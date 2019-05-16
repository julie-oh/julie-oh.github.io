---
title: OS (Operation System)
categories: memoization(kr)
auth: Julie-Oh
layout: post
---

# **프로세스란 무엇인가?**

----------

hard disk에 있는 프로그램(미생명체)을 실행시킴으로써 생명을 불어 넣어 생명체가 된다.(프로세스)
***곧, 정적 데이터가 메모리에*** `***적재***`***되면 생명이 있는*** `***프로세스***`


## * ****프로세스를 처음 실행시켰을 때***
----------

커널(연산, 저장, 보안, 프로그램 관리)이 메모리를 잡아줌
Text 영역에는 프로그램 코드가 올라감
Data, Heap 영역에는 프로그램을 사용하는데 필요한 변수들이 올라감
Stack 영역엔 함수라는 걸 쓰는데 function callstack



![process memory](https://paper-attachments.dropbox.com/s_D799983CF2B7A585C4B484555DF8AC5F88881A852F2BB30484616AFB0C462E26_1555156866890_image.png)




# **멀티테스킹**
----------

이렇게 여러 프로세스가 떠 있어 CPU에게 테스트를 주어 많은 일을 동시에 하는것 같지만 CPU 입장에서는 주어진 하나의 일만 처리함

![](https://upload.wikimedia.org/wikipedia/commons/thumb/9/91/CpuTimeonSingleCpuMultiTaskingSystem.svg/450px-CpuTimeonSingleCpuMultiTaskingSystem.svg.png)



# **프로세스의 구성**
----------

프로세스의 대한 정보는 PCB(Process Control Block)에 저장하게 된다.
프로세스가 생성될 때마다 *고유의 PCB가 생성*


- PID - 운영체제가 프로세스의 대한 유니크한 번호를 알아야 해당 프로세스를 진행하니까 있어야함
- 프로세스 상태 - 얘가 진행중 인건지, 대기상태인지 알 수 있는 상태
    - 생성(create), 준비(ready), 실행 (running), 대기(waiting), 완료(terminated)
- 프로그램 카운터(PC) - 운영체제가 다음으로 실행시킬 기계어를 담고 있는 메모리 주소값 (프로세스 마다 존재)
- 스케줄링 - 하나의 운영체제가 메모리에 떠 있는 프로세스의 순서를 정해 놓은 것
- 권한 - 우리가 앱에서 권한을 주고 실행하게 됨
- 프로세스 부모와 자식 프로세스 (tree 구조)
- 프로세스의 데이터와 명령어가 있는 메모리 위치를 가리키는 포인터
- …





# Context Switching
----------

CPU가 보고 있는 프로세스가 교체되는 것으로 Context Switching이 일어나면 PCB 포인터도 바뀜


![](https://paper-attachments.dropbox.com/s_D799983CF2B7A585C4B484555DF8AC5F88881A852F2BB30484616AFB0C462E26_1555159752379_image.png)



![process status](https://mug896.github.io/bash-shell/images/process-state.png)

## 왜 사용할까유?
----------

만약 process status가 없었다면 

![](https://paper-attachments.dropbox.com/s_D799983CF2B7A585C4B484555DF8AC5F88881A852F2BB30484616AFB0C462E26_1555160278475_image.png)


이렇게 하나의 프로세스가 다 끝나야 다른 프로세스로 갈 수 있다는 느낌 (마치 커맨드 라인.. pip install ~~ )

**But, 단점이 존재…**

----------

스위칭 하면서 레이턴시 비용이 총 CPU가 계산해야 할 시퀀스에 합산 속도는 느려짐. 
그래서 생겨난 비동기 처리방식(콜백 처리방식)


# Processing의 종류
----------

**multi-processing**(개발): 프로세스를 여러개 사용해서 연산을 동시에 하는 것
**multi-tasking**(CPU): 실제로는 동시에 하는거 아님 하는 것처럼 보임(c.s)
**concrunt-programing**(개발): 동시성 프로그래밍, 연산을 동시에 하는 것을 프로그래밍 하는 것
**parallel-programing**(개발): 병렬 프로그래밍, 진짜로 동시에 도는 것을 프로그래밍 하는 것
**multi-core programing**: 커널이 서로 다른 CPU한테 적절하게 스케쥴링 하는 것