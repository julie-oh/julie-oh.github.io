---
title: Array List & Linked List
layout: post
categories: memoization(kr)
auth: Julie-Oh
order: 4
---

# Array List란?

----------
![](https://cdn-images-1.medium.com/max/1200/0*5w9-ibvGwT1EpeH9.png)

- contiguous data on memory
- 나열 혹은 배열
- 데이터를 줄 세워 놓은 것

**그렇다면 왜 유용할까?**

----------

추상적인 개념으로는 사람이 정리/정렬된 것을 좋아함
**순서가 있는 개념**을 표현하기가 쉽다
줄세워 놓았기 때문에 → 줄을 세우는 기준 → ‘순서(order)’


- 메모리(RAM) 위에 데이터가 연속적으로 놓여져 있음
- if exists [1,2,3] of array,


**random access?**

----------
- read
- array 내의 어떤 임의의 데이터를 접근하는 것
- O(1)
- a = [1,2,34,5] (int = 32bit)
- a의 주소는 1000
- 1의 주소는 1000
- 2 → 1004
- 5 → 1016
- 99만번째의 요소의 주소는? 99만 * 4 + 1000

**insertion?**

----------
    - OS 커널이 메모리의 주소를 잡아주기 때문에.. 바로 insert가 불가
    - 그래서 다른 메모리에 주소값을 할당받아서 copy해야함
    - O(n) → copy cost
    

**deletion?**

----------
    - O(n) → copy cost
    

**modification?**

----------
    - O(1)
    - random accsess


# Linked List란?
----------
![](https://cdn-images-1.medium.com/max/1600/1*LCvUw4JaCiovZWeXb5zrMw.jpeg)



- 줄세우는건 같음
- 하지만 Array와 달리 continuos 할 필요 없음
- 한 노드는 다음 노드의 주소값을 가지고 있어야 함
- 하지만 마지막 노드는 다음 값 주소가 null
- a = [1,2,3,4,5]

**random access, modification?**

----------
- 첫번째 또는 마지막 인덱스 → O(1)
- 미들 인덱스 → Search time이 필요하므로 O(n)

**insertaion, deletion?**

----------

보편적으로 append를 할 때에는 마지막 인덱스에 추가가 됨
Array와 달리 copy cost가 생기지 않고 메모리에 바로 할당을 받아서 마지막 노드에 새로 생긴 노드의 주소값만 추가해주면 되므로 Array보다 좀 더 편한 

- 첫번째 또는 마지막 인덱스 → 인스턴스에서 첫번째와 마지막 인덱스의 주소값을 알고 있기 때문에 O(1)
- 미들 인덱스 → O(n)