---
title: 'Tree : Data Structure'
layout: post
categorise: memoization(kr)
auth: Julie-Oh
order: 5
---

# Tree : Data Structure


----------

**Tree에서 알아야 할 단어**

    Root, Parent, Child, Leaf, Sibling(시블링), Branch
    , Descendent(디센던트, 자손), Ascendent(어센던트, 조상), sub tree
    , depth(height), level(층 단위), maximum height(height 중 가장 큰 높이) 
# 
# 트리 특징
----------
1. Root는 한개임
2. 다른 모든 node를 방문할 수 있는 노드는 한개이고 그것은 루트이다
3. Leaf의 child 노드는 0개
4. 모든 노드는 sub tree의 루트이다
5. 리컬시브(재귀적)한 데이터 구조이다
6. leaf 노드부터 root까지 갈 때 branch의 갯수는 높이(height)이다.


# Binary Tree
----------

노드당 child node 최대 개수가 두 개인 것


![](https://helloacm.com/wp-content/uploads/2019/04/binary-tree-binary-numbers.jpg)


perfect, complete 등 정의는 많지만 제일 중요한 것은 balancing tree structure가 아닌가 싶다.
**balanced**: maximum height - minimum height 의 값이 1 이하 인 것


# Binary Search Tree (BST)
----------

Big O notaion → O(log n) : 뭔가를 할 때 반으로 쪼개진다

Search / insert(add) / delete : O(log n)

in-order successor: 내가 지워졌을 때 내 오른쪽에서 있는 서브 트리중 제일 작은 거