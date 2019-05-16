---
title: Stack & Queue
categories: memoization(kr)
auth: Julie-Oh
layout: post
---

# Stack?

----------
![](https://i.imgur.com/DaNczdX.png)

- 리스트에서 제일 먼저 들어온 데이터가 제일 마지막으로 빠져 나가는 자료구죠 (**FILO**, First-In-[L](https://i.imgur.com/DaNczdX.png)ast-Out)


## Big-O notaion **ㄱㄱ**
----------
- in case of Array 
    - push? O(n)
    - pop? O(1)
    - peek? O(1)
- in case of Linked List
    - push? O(1)
    - pop? O(1)
    - peek? O(1)
    
## When using Stack?
----------
- call stack


    def a():
      yeonjoo_is_love = 1
      yeonjoo_is_love = b(yeonjoo_is_love)
      yeonjoo_is_love = str(yeonjoo_is_love)
    
      return yeonjoo_is_love
    
    // text section or code section

하지만 function exception일 때에는 stack을 강제종료 하고 나오게 됨


- Balancing of symbols
    // brace
    if (yeon_joo is love) {
      foreach (yeon_joo as value) {
        print(True)
      }
    }
    // tage
    <html>
      <body>
        <a href="www.naver.com"></a>
      </body>
    <html>

  


# Queue?
----------
![](https://i.imgur.com/GXkBmm4.png)


먼저 들어온 애가 제일 먼저 탈출하는 자료구조 (FIFO, First-In-First-Out)


## 다시 한번 Big O ㄱㄱㄱㄱ
----------
- in case of Array
    - enqueue? O(n) → copy cost
    - dequeue? O(n)


- in case of Linked list (sigly linked list)
    - enqueue? O(1)
    - dequeue? O(n)


# deque(Double-ended Queue)?
----------
![](https://iq.opengenus.org/content/images/2018/05/image.PNG)

- 앞 뒤 모두 insert, delete가 가능 


    push_front(), pop_back()
    push_back(), pop_front


- 중간에 있는 데이터의 처리를 하기 힘듦


## when using deque?
----------

thread를 처리하는 방식 중에 Work Stealing 방식은 deque를 사용한다.
n개의 thread가 working 중이라고 생각해보자.
하나의 작업을 맡게된 thread는 pop_front()를 하며 작업을 진행한다.
다른 thread가 본인의 작업 할당량을 모두 처리하고 다른 thread의 작업을 가져와 처리할 때에는 pop_back()을 이용하여 처리한다.
그 이유는 본인 작업량을 처리할 때 순서대로 처리해야 조금 더 빨리 처리가 가능하다고 한다.(아마 caching과 관련있을 것으로 예상됨)
그래서 다른 thread의 일을 가져올 때에는 제일 뒤에 있는 작업을 훔쳐간다고 한다.



# priority queue?
----------
![](https://paper-attachments.dropbox.com/s_8F0042FFAF772395452B5E201CE700C71144FC764C3A6731586CB9E606B62256_1557639020003_image.png)

- queue에 우선순위에 맞춰서 넣어주는 것
- heap을 이용해 구현
- heap node를 통하여 구현