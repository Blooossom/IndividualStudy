# Browser 렌더링 과정

<aside>
💡 브라우저

</aside>

- Chrome, Safari, Firefox, IE 등
- 웹에서 페이지를 찾아서 보여주고, 사용자가 하이퍼링크를 통해 다른 페이지로 이동할 수 있도록 하는 프로그램이라고 설명
- 브라우저는 유저가 선택한 자원을 서버로부터 받아와서 유저에게 보여줌
- 이 자원은 페이지 외에도 이미지, 비디오 등의 컨텐츠들도 포함
- 받아온 자원들을 렌더링 과정을 통해 유저에게 보여줌

<aside>
💡 브라우저 렌더링 동작 과정

</aside>

1. HTML 파일과 CSS 파일을 파싱해서 각각 Tree를 만듦(Parsing)
2. 두 Tree를 결합하여 Rendering Tree를 만듦(Style)
3. Rendering Tree에서 각 노드의 위치와 크기를 계산(Layout)
4. 계산된 값을 이용하여 각 노드를 화면 상의 실제 픽셀로 변환하고, 레이어를 만듦(Paint)
5. 레이어를 합성하여 실제 화면에 나타냄(Composite)

<aside>
💡 Parsing

</aside>

- 브라우저가 페이지를 렌더링하려면 가장 먼저 받아온 HTML 파일을 해석해야 함
- Parsing 단계는 HTML 파일을 해석하여 DOM(Document Object Model) Tree를 구성하는 단계
- 파싱 중 HTML에 CSS가 포함되어 있다면 CSSOM(CSS Object Model) Tree 구성 작업도 함께 진행

<aside>
💡 Style

</aside>

- Style 단계에서는 Parsing 단계에서 생성된 DOM Tree와 CSSOM Tree를 매칭시켜서 Render Tree를 구성
- Render Tree는 실제 화면에 그려질 Tree
- 예를 들어 Render Tree를 구성할 때 visiblity:hidden은 요소가 공간을 차지하고 보이지만 않기 때문에 Render Tree에 포함이 되지만, display:none의 경우 Render Tree에서 제외

<aside>
💡 Layout

</aside>

- Layout 단계에서는 Render Tree를 화면에 어떻게 배치해야 할 것인지 노드의 정확한 위치와 크기를 계산
- 루트부터 노드를 순회하면서 노드의 정확한 크기와 위치를 계산하고 Render Tree에 반영
- 만약 크기 값을 %로 지정하였다면 Layout 단계에서 %값을 계산해서 픽셀 단위로 변환

<aside>
💡 Paint

</aside>

- Paint 단계에서는 Layout 단계에서 계산된 값을 이용해 Render Tree의 각 노드를 화면 상의 실제 픽셀로 변환
- 이 때 픽셀로 변환된 결과는 하나의 레이어가 아니라 여러 개의 레이어로 관리
- 당연한 말로 스타일이 복잡할수록 Paint 시간도 증가

<aside>
💡 Composite

</aside>

- Composite 단계에서는 Paint 단계에서 생성된 레이어를 합성하여 실제 화면에 나타냄
