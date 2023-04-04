---
layout: post
current: post
cover:  assets/built/images/deeplearning.png
navigation: True
title : (Pytorch) DistributedDataParallel 이용한 분산처리
date: 2022-11-08 11:00:00
tags: [ML]
class: post-template
subclass: 'post tag-ML'
author: crosstar
use_math: true
---


> pytorch 이용한 gpu 분산처리에 대하여 포스팅을 위해 작성하게 되었다.  

### Distributed Data parallel VS Data Parallel
- Distributed Data parallel은 multiprocessing, DataParallel은 multithreading
- Distributed Data parallel이 **single_node multi GPU 학습**에서 더 성능이 좋기 때문에, 여러 개의 GPU를 사용하면 이걸 사용


### DistributedDataParallel
- batch dimension으로 chunking을 진행함 (4대의 GPU/ batch size=128일 경우, 32씩 4개의 batch로 나뉘어짐)
- backprop 진행 시 gradient는 **평균**내어져 업데이트됨

## torch.distributed 패키지의 함수들
1. init_process_group()
   - process group을 알맞게 초기화
   - spawning process라고 함
2. DDP
   ```angular2html
    model = DDP(
    model,
    device_ids=[args.local_rank],
    output_device=args.local_rank,
    broadcast_buffers=False,
    find_unused_parameters=False,)
   
- DDP는 model state를 local rank 0로부터 다른 process(다른 GPU)로 broadcast 함
- 때문에 initial state(parameter)는 process별로 모두 같음


3. broadcast(tensor, src, group)
   - Tensor를 src로부터 모든 다른 process에 복사
4. all_reduce(tensor, dst, op, group)
   - op(함수)를 모든 tensor에 적용하고 dst에 저장
5. torch.distributed.barrier()
   - group이 함수에 들어갈 때 까지 group에 있는 모든 process를 막는다.

### communication
- DDP 는  collective communications 를 사용하여 gradient와 buffer를 동기화(synchronize)
- DDP는 각 parameter에  autograd hook을 등록하고, 해당 gradient 가 backward pass에서 계산될 때 hook 이 'fire'
- DDP는 이때 signal을 process 간 gradient synchronization에 사용!
- 
- DDP process는 같은 machine이나 machine 간에 위치할 수 있으나, GPU device는 공유될 수 없음
- 

## Reference
- https://pytorch.org/docs/stable/generated/torch.nn.parallel.DistributedDataParallel.html
- https://pytorch.org/tutorials/intermediate/ddp_tutorial.html
- https://pytorch.org/tutorials/intermediate/dist_tuto.html