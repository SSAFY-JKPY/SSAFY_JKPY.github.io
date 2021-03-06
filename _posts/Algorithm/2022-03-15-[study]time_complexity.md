---
title: "Time Complexity"
excerpt: "Study for Time Complexity"
excerpt_separator: "<!--more-->"
author: "CH"
categories:
  - Algorithm
tags:
  - Basic
last_modified_at: 2022-03-15T22:42:00
---

<!--more-->

<br>

## 시간복잡도(Time Complexity)의 표기법

### O-표기법

- O(g(n))은 충분히 큰 n에 대하여 f(n)<=cg(n)를 성립시키는 양의 상수 c를 가지고 있음을 의미한다.
- 달리 표현하면, O(g(n))은 최악의 경우에도 점근적 증가율이 g(n)을 넘지 않음을 의미한다.

### Ω-표기법

- Ω(g(n))은 충분히 큰 n에 대하여 c(g(n))<=f(n)을 성립시키는 양의 상수 c를 가지고 있음을 의미한다.
- 즉, Ω(g(n))은 하한의 개념을 가진다.

### θ-표기법

- θ(g(n))은 충분히 큰 n에 대하여 O(g(n))과 Ω(g(n))을 동시에 만족하는 함수 집합이다.
- 즉, c1g(n) <= f(n) <= c2g(n) 을 성립시키는 c1과 c2가 존재한다.

### o-표기법

- o(g(n))은 충분히 큰 n에 대하여 함수 증가율이 항상 f(n)보다 큰 모든 함수의 집합을 의미한다.
- 예를 들어 3n = o(n^2) 이다. 단, 5n^2 은 o(n^2)이 아니다(함수 증가율이 점근적으로 동일).

### ω-표기법

- ω(g(n))은 o(g(n))과 반대로 충분히 큰 n에 대하여 함수 증가율이 항상 f(n)보다 작은 모든 함수 집합을 의미한다.
- 예를 들어 3n^2 = ω(8n) 이다. 단, 3n^2 은 ω(n^2)이 아니다(함수 증가율이 점근적으로 동일).

## 점화식의 시간복잡도 계산법

### 반복 대치

- 점화식을 더 낮은 차수의 항으로 전개 및 변환하여 규칙을 찾고, 시간복잡도를 파악하는 방법.
- 예를 들어 factorial 과정을 보면 아래와 같은 형식으로 규칙을 찾게 된다.
  T(n) = T(n-1) + c
  = T(n-2) + c + c = T(n-2) + 2c
  = T(n-3) + c + c + c = T(n-3) + 3c
  ...
  = T(1) + (n-1)c
  <= c + (n-1)c
  = cn
  ∴ T(n) = O(n)

### 추정 후 귀납적으로 증명

- 점화식의 모양을 보고 복잡도를 유추한 뒤, 귀납적 증명법으로 명제를 증명하는 방법이다.
- 증명 과정은 귀납적 가정과 참인 명제를 이용해 증명을 하며, 반복 대치 방법으로 풀어내기도 한다.

### 특정 경우에 대한 정리

- f(n)/g(n) 에서
  1. g(n)이 클 경우, g(n)이 수행 시간 결정
  2. f(n)이 클 경우, f(n)이 수행 시간 결정
  3. f(n)==g(n)이면, g(n)에 logn을 곱한 것이 수행 시간이 된다.

## 정렬 방법별 시간복잡도

### 선택정렬(Selection Sort)

- 배열 A[1...n]에서 가장 큰(혹은 가장 작은) 원소를 찾은 뒤 가장 마지막 인덱스 원소와 위치를 서로 바꾼다. 이후 A[1...(n-1)] 에서 같은 과정을 거친다.
- 선택정렬은 원소의 수가 n에서 2까지 줄어드는 각 경우마다 (원소의 개수-1)만큼 비교를 진행하게 되므로,
  (n-1) _ (n-2) _ ... _ 2 _ 1 = n(n-1)/2 가 된다. 즉, O(n^2)이다.

### 버블정렬(Bubble Sort)

- 배열 A[1...n]에서 바로 인접해 있는 요소와 비교를 진행하여 더 큰(혹은 더 작은) 원소가 왼쪽으로 가도록 정렬한다. 이를 A[1...(n-1)] 에서 같은 과정을 거친다.
- 버블정렬은 원소의 수가 n에서 2까지 줄어드는 각 경우마다 (원소의 개수-1)만큼 비교를 진행하게 되므로,
  (n-1) _ (n-2) _ ... _ 2 _ 1 = n(n-1)/2 가 된다. 즉, O(n^2)이다.

### 삽입정렬(Insertion Sort)

- 삽입정렬은 배열 A[1...n]에서 요소를 차례대로 탐색하여 왼쪽 부분배열에 요소를 순서에 맞게 삽입하며 정렬한다.
- 최고의 경우에는 배열이 이미 정렬되어 있어 상수 횟수의 시간복잡도를 가질 수 있다.
- 최악의 경우에는 탐색된 요소가 A[1]자리에 계속해서 들어가게 되는데, 이 때의 시간복잡도는
  1 + 2 + ... + (n-1) = n(n-1)/2, 즉 O(n^2)이 된다.

### 병합정렬(Merge Sort)

- A[n]의 배열을 반으로 나눈 뒤 각각을 정렬하고, 두 배열을 다시 하나로 합치는 과정의 정렬 방법이다.
- 합치는 과정에서는 나눠진 두 배열의 요소들을 정렬 기준에 따라 하나씩 추출하여 정렬한다.
  ![병합정렬 시간복잡도입니다.](/assets/img/MergeSort.jpg)

### Heap Sort

- 힙(Heap)이란 이진 트리의 자료구조로, 최소 힙과 최대 힙으로 나눌 수 있다.
- 힙의 특징
  - 마지막 레벨을 제외한 각 레벨의 노드는 모두 채워져야 한다.
  - 마지막 레벨에서는 왼쪽부터 채워져야 한다.
  - 최소 힙의 경우 부모 노드가 자식 노드보다 항상 작거나 같으며, 최대 힙의 경우 부모 노드가 항상 자식 노드보다 크거나 같다.
    ![힙정렬 시간복잡도입니다.](/assets/img/HeapSort.jpg)

### Quick Sort

- 평균적으로 가장 좋은 성능을 가진 정렬 알고리즘.
- 기준 원소를 두고, 기준 원소보다 작은 원소는 왼쪽에 큰 원소는 오른쪽에 두며 정렬한다. 마지막에는 작은 원소와 큰 원소 사이의 경계에 기준 원소를 위치시킨다.
  ![퀵정렬 시간복잡도입니다.](/assets/img/QuickSort.jpg)
