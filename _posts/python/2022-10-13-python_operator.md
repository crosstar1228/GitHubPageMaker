---
layout: post
current: post
cover:  assets/built/images/algorithm_background.jpg
navigation: True
title: (python중급) 깔끔하게 함수 리모델링해보자! itemgetter, attrgetter, methodcaller, partial
date: 2022-10-13 11:00:00
tags: [python]
class: post-template
subclass: 'post tag-ML'
author: crosstar
use_math: true
---


> Keyword : operator, itemmgetter, attrgetter, methodcaller

### Operator
- python operator 모듈 안에는 다양한 함수들이 있음
- 활용해서 가독성 있는 코딩이 가능함

### itemgetter
- index가 정해져있는 함수를 반환함
```
arr = ['a', 'b', 'c']
func = itemgetter(2)

func(arr) 
>>> 'b'
```

### attrgetter
- class의 attribute이름을 특정하면 그 attribute를 반환

```angular2html
f = attrgetter('name')
f(b)
>> b.name
```
- 여러개의 attribute나 중첩된 attribute 형태도 가능함

### methodcaller
- class의 method 특정해서 그 결과값을 반환
- *args, **kwargs 등을 입력해서 해당 method input을 바로 입력하는 것도 가능!

```angular2html
 f = methodcaller('name', 'foo', bar=1)
f(b) 
>>> b.name('foo', bar=1)
```


## functools.partial
- 하나 이상의 인수가 채워진 또 하나의 함수를 만드는 데 사용
- 불필요한 반복작업 줄임


```
# 첫 인자에 따라 더하기도 하고, 곱하기도 하는 함수
def add_mul(choice, *args):
    if choice == "add":
        result = 0
        for i in args:
            result = result + i
    elif choice == "mul":
        result = 1
        for i in args:
            result = result * i
    return result


# 더하는 함수를 만드는 일반적인 풀이 
def add(*args):
    return add_mul('add', *args)
    
# partial 사용할 경우 간결해진다! 
add = partial(add_mul, 'add')

```
### 회고
- 코드 가독성을 높이는 데 좋을 듯 하다.
- 다른 여러 사칙.논리 연산 등에도 유용해 보인다(공식문서 참고).
- partial은 활용도가 높아 보인다. 

## Reference
- https://docs.python.org/3/library/operator.html
- https://wikidocs.net/109304