# 로드 밸런싱
<aside>
<h2>💡 로드 밸런싱?</h2>

</aside>

- 로드 밸런싱은 **애플리케이션을 지원하는 리소스 풀 전체에 네트워크 트래픽을 균등하게 배포하는 방법**
- 최신 애플리케이션은 수백만 명의 사용자를 동시에 처리하고 정확한 텍스트, 비디오, 이미지 및 기타 데이터를 빠르고 안정적인 방식으로 각 사용자에게 반환해야 함
- 이렇게 많은 양의 트래픽을 처리하기 위해 대부분의 애플리케이션에는 데이터가 중복되는 리소스 서버가 많이 있음
- 로드 밸런서는 사용자와 서버 그룹 사이에 위치하며 보이지 않는 촉진자 역할을 하며 모든 리소스 서버가 동일하게 사용되도록 하는 디바이스


<aside>
  <br>
<h2>💡 로드 밸런싱의 이점</h2>

</aside>

- 로드 밸런싱은 애플리케이션 서버와 방문자 또는 클라이언트 간의 인터넷 트래픽을 지시하고 제어
- 결과적으로 애플리케이션의 가용성, 확장성 보안 및 성능이 향상
- 애플리케이션 가용성
    - 서버 장애 또는 유지 관리로 인해 애플리케이션 가동 중지 시간이 늘어 방문자가 애플리케이션을 사용할 수 없게 될 수 있음
    - 로드 밸런서는 서버 문제를 자동으로 감지하고 클라이언트 트래픽을 사용 가능한 서버로 리디렉션하여 시스템의 내결함성을 높임
    - 로드 밸런싱을 사용하여 아래 작업을 더 쉽게 수행할 수 있음
        - 애플리케이션 가동 중지 없이 애플리케이션 서버 유지 관리 또는 업그레이드 실행
        - 백업 사이트에 자동 재해 복구 제공
        - 상태 확인을 수행하고 가동 중지를 유발할 수 있는 문제 방지
         <br>
- 애플리케이션 확장성
    - 로드 밸런서를 사용하여 여러 서버 간에 네트워크 트래픽을 지능적으로 전달할 수 있음
    - 로드 밸런싱이 다음을 수행하므로 애플리케이션에서 수천 개의 클라이언트 요청을 처리할 수 있음
        - 한 서버에서 트래픽 병목 현상을 방지
        - 필요한 경우 다른 서버를 추가하거나 제거할 수 있도록 애플리케이션 트래픽을 예측
        - 안심하고 조정할 수 있도록 시스템에 중복성을 추가
        <br>
- 애플리케이션 보안
    - 로드 밸런서에는 인터넷 애플리케이션에 또 다른 보안 계층을 추가할 수 있는 보안 기능이 내장되어 있음
    - 이는 공격자가 서버 장애를 일으키는 수백만 개의 동시 요청으로 애플리케이션 서버를 가득 채우는 분산 서비스 거부 공격을 처리하는 데 유용함
    - 로드 밸런서는 다음을 수행할 수 도 있음
        - 트래픽 모니터링 및 악성 콘텐츠 차단
        - 공격 트래픽을 여러 백엔드 서버로 자동으로 리디렉션하여 영향 최소화
        - 추가 보안을 위해 네트워크 방화벽 그룹을 통해 트래픽 라우팅
        <br>
- 애플리케이션 성능
    - 로드 밸런서는 응답 시간을 늘리고 네트워크 지연 시간을 줄여 애플리케이션 성능을 향상 시킴
        - 서버 간에 로드를 균등하게 배포하여 애플리케이션 성능 향상
        - 클라이언트 요청을 지리적으로 더 가까운 서버로 리디렉션하여 지연 시간 단축
        - 물리적 및 가상 컴퓨팅 리소스의 신뢰성 및 성능 보장

<aside>
  <br>
<h2>💡 로드 밸런싱 알고리즘</h2>

</aside>

- 로드 밸런싱 알고리즘은 로드 밸런서가 서로 다른 클라이언트 요청 각각에 가장 적합한 서버를 결정하기 위해 따르는 규칙 세트
- 로드 밸런싱 알고리즘은 크게 2가지 범주로 나뉨
- 정적 로드 밸런싱
    - 정적 로드 밸런싱 알고리즘은 고정된 규칙을 따르며 현재 서버 상태와 무관
    - 아래는 정적 로드 밸런싱의 예
        - 라운드 로빈
            - 서버에는 클라이언트에게 요청으 ㄹ전송할 위치를 알려주는 IP 주소가 있음
            - IP 주소는 기억하기 어려운 긴 숫자
            - 이를 쉽게 하기 위해 도메인 이름 시스템은 웹 사이트 이름을 서버에 매핑
            - 브라우저에 aws.amazon.com을 입력하면 먼저 요청이 당사의 이름 서버로 전달하고 이름 서버는 IP주소를 브라우저로 반환
            - 라운드 로빈 방식에는 권한 있는 이름 서버가 특수 하드웨어나 소프트웨어 대신 로드 밸런싱을 수행
            - 이름 서버는 서버 팜에 있는 여러 서버의 IP 주소를 차례대로 또는 라운드 로빈 방식으로 반환
            <br>
        - 가중 기반 라운드 로빈
            - 가중치 기반 라운드 로빈 밸런싱에서는 우선순위 또는 용량에 따라 각 서버에 서로 다른 가중치를 할당할 수 있음
            - 가중치가 높은 서버는 이름 서버에서 들어오는 애플리케이션 트래픽을 더 많이 수신
            <br>
        - IP 해시
            - IP 해시 방법에서는 로드 밸런서는 클라이언트 IP 주소에 대해 해싱이라고 하는 수학적 계산을 수행
            - 클라이언트 IP 주소를 숫자로 변환한 다음 개별 서버에 매핑
            <br>
- 동적 로드 밸런싱
    - 동적 로드 밸런싱은 트래픽을 배포하기 전에 서버의 현재 상태를 검사
    - 다음은 동적 로드 밸런싱 알고리즘의 몇 가지 예제
        - 최소 연결 방법
            - 연결은 클라이언트와 서버 간의 개방형 통신 채널
            - 클라이언트는 서버에 첫 번째 요청을 전송할 때 서로 활성 연결을 인증하고 설정
            - 최소 연결 방법에는 로드 밸런서는 활성 연결이 가장 적은 서버를 확인하고 해당 서버로 트래픽을 전송
            - 이 방법에서는 모든 연결에 모든 서버에 대해 동일한 처리 능력이 필요하다고 가정
            <br>
        - 가중치 기반 최소 연결 방법
            - 가중치 기반 최소 연결 알고리즘은 일부 서버가 다른 서버보다 더 많은 활성 연결을 처리할 수 있다고 가정
            - 따라서 각 서버에 다른 가중치 또는 용량을 할당할 수 있으며 로드 밸런서는 용량별 연결이 가장 적은 서버로 새 클라이언트 요청을 전송
            <br>
        - 최소 응답 시간 방법
            - 응답 시간은 서버가 들어오는 요청을 처리하고 응답을 전송하는 데 걸리는 총 시간
            - 최소 응답시간 방법은 서버 응답 시간과 활성 연결을 결합하여 최상의 서버를 결정
            - 로드 밸런서는 이 알고리즘을 사용하여 모든 사용자에게 더 빠른 서비스를 보장
            <br>
        - 리소스 기반 방법
            - 리소스 기반 방법에서는 로드 밸런서는 현재 서버 부하를 분석하여 트래픽을 배포
            - 에이전트라고 하는 특수 소프트웨어는 각 서버에서 실행되며 컴퓨팅 용량 및 메모리와 같은 서버 리소스의 사용량을 계산
            - 그런 다음 로드 밸런서는 해당 서버에 트래픽을 배포하기 전에 에이전트에 충분한 여유 리소스가 있는 지 확인
        

<aside>
  <br>
<h2>💡 Layer 4 로드 밸런싱, Layer 7 로드 밸런싱</h2>

</aside>

- 로드 밸런싱에는 Layer 4, Layer 7 로드 밸런싱이 가장 많이 활용
- 두 레이어는 OSI 7 Layer에서 전송, 응용계층 프로토콜의 헤더를 부하 분산에 이용하기 때문에 붙은 접두사
- 모든 요청을 L4, L7 로드 밸런서가 받아 서버들에게 적절히 나누어 줌
- L4 로드 밸런서는 네트워크 계층(IP, IPX)이나 전송 계층(TCP, UDP)의 정보(IP주소, 포트번호, MAC주소, 전송 프로토콜)를 바탕으로 로드를 분산
- L7 로드 밸런서는 애플리케이션 계층(HTTP, FTP, SMTP)에서 로드를 분산하기 때문에 HTTP 헤더, 쿠키 등과 같은 사용자의 요청을 기준으로 특정 서버에 트래픽을 분산하는 것이 가능
- 쉽게 말해 패킷의 내용을 확인하고 그 내용에 따라 로드를 특정 서버에 분배하는 것이 가능
- URL에 따라 부하를 분산시키거나, HTTP 헤더의 쿠키 값에 따라 부하를 분산하는 등 클라이언트의 요청을 보다 세분화해 서버에 전달할 수 있음
- 또한 L7 로드 밸런서의 경우 특정한 패턴을 지닌 바이러스를 감지해 네트워크를 보호할 수 있으며 DoS.DDoS와 같은 비정상적인 트래픽을 필터링할 수 있어 네트워크 보안 분야에서도 활용되고 있

<aside>
  <br>
<h2>💡 로드 밸런싱의 작동</h2>

</aside>

- 회사는 일반적으로 여러 서버에서 애플리케이션을 실행
- 이러한 서버 배열을 서버 팜이라고 함
- 애플리케이션에 대한 사용자 요청은 먼저 로드 밸런서로 이동
- 그런 다음 로드 밸런서는 요청을 처리하는 데 가장 적합한 서버 팜의 단일 서버로 각 요청을 라우팅

- 로드 밸런싱은 레스토랑에서 관리자가 수행하는 작업과 같음
- 5명의 웨이터가 있는 식당을 예로 들 때 고객이 웨이터를 선택할 수 있는 경우 한 두 명의 웨이터는 업무에 과부하가 걸리고 나머지는 유휴 상태일 수 있음
- 이러한 경우가 발생하지 않도록 레스토랑 관리자는 고객에게 가장 적합한 특정 웨이터에게 고객을 할당함

<aside>
  <br>
<h2>💡 로드 밸런싱 유형</h2>

</aside>

- 로드 밸런서가 트래픽을 리디렉션 하기 위해 클라이언트 요청에서 확인하는 콘텐츠에 따라 로드 밸런싱을 3가지 주요 범주로 분류할 수 있음
- 애플리케이션 로드 밸런싱
    - 복잡한 최신 애플리케이션에는 단일 애플리케이션 기능을 전담하는 여러 서버를 포함하는 여러 서버팜이 존재
    - Application Load Balancer는 HTTP 헤더 또는 SSL 세션 ID와 같은 요청 콘텐츠를 확인하여 트래픽을 리디렉션
    - 예를 들어 전자 상거래 애플리케이션에는 제품 디렉토리, 장바구니 및 결제 기능이 존재
    - Application Load Balancer는 이미지와 비디오를 포함하지만 열린 연결을 유지할 필요가 없는 서버에 제품 검색 요청을 전송
    - 이에 비해 많은 클라이언트 연결을 유지하고 장바구니 데이터를 오랫동안 저장할 수 있는 서버로 장바구니 요청을 전송
- 네트워크 로드 밸런싱
    - Network Load Balancer는 IP 주소 및 기타 네트워크 정보를 검사하여 트래픽을 최적으로 리디렉션함
    - 애플리케이션 트래픽의 소스를 추적하고 여러 서버에 고정 IP 주소를 할당
    - Network Load Balancer는 앞에서 설명한 고적 및 동적 로드 밸런싱 알고리즘을 사용하여 서버 로드를 배포
- 글로벌 서버 로드 밸런싱
    - 글로벌 서버 로드 밸런싱은 지리적으로 분산된 여러 서버에서 발생합니다
    - 예를 들어 회사는 여러 데이터 센터, 여러 국가 및 전 세계의 타사 클라우드 제공업체에 서버를 둘 수 있음
    - 이 경우 로컬 로드 밸런서는 리전 또는 영역 내에서 애플리케이션 로드를 관리
    - 그리고 클라이언트와 지리적으로 더 가까운 서버 대상으로 트래픽을 리디렉션하려고 함
    - 서버 장애가 발생한 경우에만 클라이언트는 지리적 영역 외부의 서버로 트래픽을 리디렉션
- DNS 로드 밸런싱
    - DNS 로드 밸런싱에서는 도메인의 리소스 풀에서 네트워크 요청을 라우팅하도록 도메인을 구성
    - 도메인은 웹 사이트, 메일 시스템, 인쇄 서버 또는 인터넷을 통해 액세스할 수 있는 다른 서비스에 해당할 수 있음
    - DNS 로드 밸런싱은 애플리케이션 가용성을 유지하고 전역적으로 분산적으로 리소스 풀에서 네트워크 트래픽을 분산하는 데 유용

<aside>
  <br>
<h2>💡 로드 밸런싱 기술 유형</h2>

</aside>

- 하드웨어 로드 밸런서
    - 하드웨어 기반 로드 밸런서는 수 기가바이트의 트래픽을 안전하게 처리하고 수백 개의 서로 다른 서버로 리디렉션할 수 있는 하드웨어 어플라이언스
    - 데이터 센터에 저장하고 가상화를 사용하여 중앙에서 관리할 수 있는 여러 디지털 또는 가상 로드 밸런서를 만들 수 있음
    
- 소프트웨어 로드 밸런서
    - 소프트웨어 기반 로드 밸런서는 모든 로드 밸런싱 기능을 수행하는 애플리케이션
    - 소프트웨어 로드 밸런서를 모든 서버에 설치하거나 완전관리형 타사 서비스로 액세스 할 수 있음
- 하드웨어 로드 밸런서 VS 소프트웨어 로드 밸런서
    - 하드웨어 로드 밸런서는 초기 투자, 구성 및 지속적인 유지 관리가 필요
    - 또한 최대 용량으로 하드웨어 로드 밸런서를 사용하지 않을 수도 있음
    - 특히 피크 시간 트래픽 급증을 처리하는 용도로만 하드웨어 로드 밸런서를 구매하는 경우 더욱 그러함
    - 트래픽 볼륨이 현재 용량을 초과하여 급증하면 다른 로드 밸런서를 구매하여 설정할 수 있을 때까지 사용자에게 영향이 있음
    - 반대로 소프트웨어 기반 로드 밸런서는 훨씬 더 유연함
    - 쉡게 스케일 업하거나 스케일 다운할 수 있으며 최신 클라우드 컴퓨팅 환경과 더 잘 호환
    - 또한 시간이 지남에 따라 설정, 관리 및 사용하는 데 드는 비용도 줄어듦

<aside>
  <br>
<h2>💡 참조</h2>

</aside>

[로드 밸런싱이란 무엇인가요? - 로드 밸런싱 알고리즘 설명 - AWS](https://aws.amazon.com/ko/what-is/load-balancing/)

[로드 밸런싱에 대해 알아보자!](https://tecoble.techcourse.co.kr/post/2021-11-07-load-balancing/)
