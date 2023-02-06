# Linked List
    
<aside>
  <h2>💡 개요</h2>
    
</aside>
    
- 여기서 연결은 무엇인가
- Linked List는 Array List와 다르게 요소와 요소 간의 연결을 이용해서 리스트를 구현한 것을 의미함

<br>
<aside>
<h2>💡 연결?</h2>

</aside>

- Linked List의 이름에 왜 연결을 의미하는 링크는
- 배열과 다르게 그 위치가 흩어져 있기 때문에 서로 연결되어 있어야 함
- 바로 그런 점에서 연결이라는 이름을 갖게 된 것
- Array List에서는 엘리먼트라는 이름을 사용했지만 linked list와 같이 연결된 엘리먼트들은 노드 혹은 버텍스라고 부름

<br>
<aside>
<h2>💡 구조</h2>

</aside>

- Linked List는 노드들의 모임
- 따라서 내부적으로 노드를 가지고 있어야 함
- 노드는 최소한 두 가지 정보를 알고 있어야 하는데
- 노드의 값과 다음 노드에 대한 정보임
- 각각의 노드가 다음 노드를 알고 있기 때문에 하나의 연결된 값의 모임을 만들 수 있는 것
<br>
<aside>
<h2>💡 데이터의 추가 삭제</h2>

</aside>

- 배열의 경우 요소를 중간에 추가 삭제할 경우 해당 요소 뒤에 있는 모든 요소의 자리 이동이 필요
- 따라서 배열은 추가/삭제가 느림
- 반대로 Linked List의 추가/삭제가 될 엘리먼트의 이전 이후 노드의 참조값만 변경하면 되기 때문에 속도가 빠름
- 반면 탐색에 있어서는 Linked List는 데이터를 조회할 때 head가 가리키는 노드부터 시작해서 순차적으로 노드를 찾아가는 과정을 거쳐야 함
- 만약 찾고자 하는 노드가 가장 끝에 있으면 모든 노드를 탐색해야함..