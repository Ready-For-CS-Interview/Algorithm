# Algorithm

---

## Index
1. [정렬](#1-정렬)
2. [Problem Solving Paradigm](#2-problem-solving-paradigm)
3. [질문 및 답변](#3-질문-및-답변)

---

## 1. 정렬

<details>
<summary>1-1. Insertion Sort</summary>
<a href="https://velog.io/@jooon/%EC%95%8C%EA%B3%A0%EB%A6%AC%EC%A6%98-Insertion-Sort" target="_blank">
Insertion Sort 정리글
</details>

<details>
<summary>1-2. Selection Sort</summary>
<a href="https://velog.io/@jywon/선택-정렬" target="_blank">
Selection Sort 정리글
</a>
</details>

<details>
<summary>1-3. Bubble Sort</summary>
<a href="https://velog.io/@geooeg/%EC%95%8C%EA%B3%A0%EB%A6%AC%EC%A6%98-Bubble-Sort" target="_blank">
Bubble Sort 정리글
</a>
</details>

<details>
<summary>1-4. Quick Sort</summary>
<a href="https://velog.io/@jywon/퀵-정렬" target="_blank">
Quick Sort 정리글
</a>
</details>

<details>
<summary>1-5. Merge Sort</summary>
<a href="https://velog.io/@jooon/%EC%95%8C%EA%B3%A0%EB%A6%AC%EC%A6%98-Merge-Sort" target="_blank">
Merge Sort 정리글
</details>

<details>
<summary>1-6. Heap Sort</summary>
<a href="https://velog.io/@geooeg/%EC%95%8C%EA%B3%A0%EB%A6%AC%EC%A6%98-Heap-Sort" target="_blank">
Heap Sort 정리글 
</a>
</details>

<details>
<summary>1-7. Counting Sort</summary>
<a href="https://velog.io/@jywon/계수-정렬" target="_blank">
Counting Sort 정리글
</a>
</details>

<details>
<summary>1-8. Radix Sort</summary>
<a href="https://velog.io/@geooeg/%EC%95%8C%EA%B3%A0%EB%A6%AC%EC%A6%98-Radix-Sort" target="_blank">
Radix Sort 정리글 
</a>
</details>

---

## 2. Problem Solving Paradigm
<details>
<summary>2-1. Dynamic Programming</summary>
<a href="https://velog.io/@jooon/%EC%95%8C%EA%B3%A0%EB%A6%AC%EC%A6%98-DP-LIS" target="_blank">
Dynamic Programing 정리글 
</details>

<details>
<summary>2-2. Greedy Algorithm</summary>
<a href="https://velog.io/@geooeg/%EC%95%8C%EA%B3%A0%EB%A6%AC%EC%A6%98-Greedy-Algorithm" target="_blank">
Greedy Algorithm 정리글 
</a>
</details>

<details>
<summary>2-3. 재귀</summary>
<a href="https://velog.io/@jywon/재귀#반복문" target="_blank">
재귀 정리글
</details>

<details>
<summary>2-4. LCA</summary>
<a href="https://velog.io/@jywon/최소-공통-조상-LCA" target="_blank">
LCA 정리글
</details>

<details>
<summary>2-5. BitMask</summary>
<a href="https://velog.io/@geooeg/%EC%95%8C%EA%B3%A0%EB%A6%AC%EC%A6%98-BitMask" target="_blank">
BitMask 정리글 
</a>
</details>

---

## 3. 질문 및 답변

<details>
<summary><b>Sort를 분류할 수 있는 기준이 무엇이 있는지</b></summary>
1. 비교 기반인지 아닌지이다.
버블, 삽입, 퀵, 머지처럼 두 값을 직접 비교해서 정렬하는 방식이 있고, 계수 정렬이나 기수 정렬처럼 값 자체를 기준으로 분류하는 방식도 있다.
비교 기반은 이론적으로는 O(n log n)이 최선이고, 비교하지 않는 방식은 조건이 맞으면 O(n)에 동작할 수도 있다.

2. 안정 정렬(stable sort) 여부다.
동일한 값이 여러 개 있을 때 입력 순서를 그대로 유지하는지인데, 머지 정렬이나 삽입 정렬은 안정 정렬이고, 퀵 정렬이나 힙 정렬은 불안정하다.
만약 정렬 후에도 순서 정보가 의미가 있을 경우엔 안정 정렬을 선택해야 한다.

3. 정렬을 언제 수행하느냐, ****즉 온라인 정렬이 가능한지다.
삽입 정렬이나 힙 정렬은 데이터가 하나씩 들어올 때마다 바로 정렬 상태를 유지할 수 있어서, 스트리밍 데이터나 실시간 처리 상황에 적합하다.

4. 시간과 공간 복잡도가 있다.
O(n²) 정렬은 단순하지만 느리고, O(n log n) 정렬은 time complexity와 space complexity 균형이 좋고,
O(n) 정렬은 빠르지만 조건이 제한적이거나 메모리를 많이 쓴다.
그래서 일반적으로는 퀵 정렬이나 인트로 정렬처럼 속도와 메모리 균형이 좋은 알고리즘을 많이 쓴다.
</details>

<details>
<summary><b>Quick Sort의 성능 개선 방법과 이를 적용한 기술</b></summary>
퀵 정렬은 평균적으로는 굉장히 빠른 정렬이지만, pivot 선택이 한쪽으로 치우치게 되면 최악의 경우 시간 복잡도가 O(n²)까지 떨어지는 단점이 있다. 이 문제를 보완하기 위해 피벗을 랜덤하게 선택하거나, 세 개의 값을 골라 그 중간값을 선택하는 median-of-three 같은 전략이 사용된다.
이런 방식들은 보다 균형 잡힌 분할을 유도해서 평균적인 성능을 높이는 데 효과적이다.
하지만 이런 전략들로도 최악의 경우를 완전히 피할 수는 없기 때문에, 실제 라이브러리 구현에서는 introsort라는 방식이 자주 사용된다. introsort는 퀵 정렬로 시작해서, 재귀 깊이가 일정 수준을 넘으면 힙 정렬로 전환해서 최악의 경우에도 O(n log n)을 보장하는 방식이다.
실제로 C++의 sort 함수나, 자바의 Arrays.sort(int[])에서 이런 방식이 사용된다.
또한 자바는 dual-pivot quicksort라는 알고리즘을 사용해서 평균적인 분할 성능을 더 높이기도 한다.
피벗을 두 개 사용해서 세 부분으로 분할하고, 그에 따라 비교 횟수나 재귀 깊이를 줄이는 방식이다.
</details>

<details>
<summary><b>다양한 정렬의 성능 하한이 O(N log N)인 이유와, 이를 개선한 방식 설명</b></summary>
N개의 원소를 정렬하는 비교 기반 알고리즘은, 입력에 따라 N! 개의 가능한 순열 중 하나를 결정합니다. 이 과정은 결정 트리로 모델링할 수 있으며, 노드는 비교 연산, 리프는 정렬된 순열입니다. 
결정 트리의 최소 높이는 log₂(N!)이고, 이는 Stirling 근사를 통해 N log N에 해당함을 알 수 있습니다. 따라서 최적의 비교 기반 정렬조차도 평균적으로 최소 N log N번의 비교가 필요하다는 것이 증명됩니다.
이러한 하한은 ‘비교 연산’을 기반으로 한 정렬에만 적용됩니다. 비교를 사용하지 않고 입력값의 특성을 활용하면 O(N log N)보다 빠른 정렬도 가능합니다.
</details>

<details>
<summary><b>시간 복잡도와 공간 복잡도의 trade-off 예시</b></summary>
메모이제이션 (Dynamic Programming)
같은 계산을 반복하지 않기 위해 결과를 메모리에 저장해두는 방식입니다. 시간 복잡도는 중복 계산을 제거하기 때문에 적지만, 결과를 저장하는 저장 공간을 필요로 해서 공간 복잡도가 증가합니다.

해시 테이블 사용
특정 값의 존재 여부나 인덱스를 빠르게 찾기 위해 배열이나 해시맵을 사용하는 방식입니다. 해시 테이블을 구현한 다음에 찾기 때문에 탐색이 O(1)에 가능하지만, 테이블을 만들어야 한다는 조건이 있기 때문에 space complexity가 큽니다.

Counting Sort
값의 범위가 작을 때 사용 가능한 정렬 알고리즘으로, 값을 인덱스로 사용하는 카운트 배열을 생성합니다.

다익스트라 알고리즘의 구현 방식
다익스트라 알고리즘에서 edge를 최소로 하는 것을 선택할 때 heap을 이용해서 최소를 선택하면 time complexity가 감소하지만, heap을 만들 공간이 필요하기 때문에 더 많은 메모리를 이용하게 됩니다.

슬라이딩 윈도우 vs 누적합
누적합(Prefix Sum)을 미리 구해두면 구간합 계산 시간은 O(1)로 빠르지만, 공간을 O(n) 더 씁니다.
슬라이딩 윈도우는 추가 공간 없이 구간합을 갱신하지만, 상황에 따라 구현이 복잡해질 수 있습니다
</details>

<details>
<summary><b>항상 divide and conquer이랑 재귀보다 DP가 좋은지</b></summary>
P가 무조건 우월하다고 보기는 어렵습니다. 먼저 세 기법의 관계를 정리해 보면, divide and conquer는 문제를 부분 문제로 쪼개서 각각 해결한 뒤 합치는 전략이고, 재귀는 이를 코드로 표현하는 한 방법입니다. DP는 divide and conquer 중에서도 ‘부분 문제들이 반복해서 등장’하고 ‘그 해답이 다시 필요’할 때, 중복 계산을 제거하기 위해 메모이제이션(Top-Down)이나 테이블(Bottom-Up)을 쓰는 특수한 형태입니다.

따라서 중복되는 하위 문제가 없거나 N이 작아 계산량이 작을 때는 굳이 DP로 변환하지 않는 편이 더 단순하고 가독성이 좋습니다. 예를 들어 병합 정렬 같은 정렬 알고리즘은 같은 구간을 두 번 이상 계산하지 않으니 순수 divide and conquer가 깔끔하고 빠릅니다. 반면 피보나치 수열처럼 ‘겹치는 부분 문제’가 많으면 재귀만 쓰면 O(2^N)이지만 DP로 바꾸면 O(N)으로 떨어집니다. 이때는 DP가 명백히 이득입니다.

백엔드 관점에서는 성능 외에 두 가지를 함께 고려합니다.
1. 메모리와 캐싱 전략
    DP는 상태를 저장하므로 힙이나 캐시에 메모리를 더 요구합니다. 런타임 환경이나 컨테이너 메모리 한도가 빡빡한 서비스라면, 시간이 조금 느려지더라도 메모리를 덜 쓰는 divide and conquer가 현실적인 선택일 수 있습니다. 반대로 서버 팟에 여유 RAM이 있고 요청 수가 많아 동일 계산이 반복된다면, DP에 해당하는 결과 캐싱을 미리 해 두는 편이 TPS를 높입니다.
2. 코드 유지보수와 안정성
    재귀를 그대로 사용하면 스택 오버플로우 위험이 있습니다. Go나 Java처럼 기본 스택 크기가 작은 런타임에서는, 깊은 재귀 호출이 예상될 때 루프나 DP로 바꿔 iterative하게 작성합니다. 또한 팀 내에서 알고리즘 숙련도가 다를 때, Bottom-Up DP가 오히려 직관적일 수 있습니다. 반면 아주 간단한 로직이라면 재귀 한두 줄이 더 읽기 쉽고 버그가 덜 생깁니다.
    
→ 중복 부분 문제가 있고 입력 크기가 커서 시간 복잡도가 병목이면 DP, 중복이 없거나 입력이 작고, 메모리가 제한적이거나 코드가 간결해야 하면 divide and conquer나 단순 재귀가 좋습니다.
</details>