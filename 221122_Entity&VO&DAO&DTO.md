<aside>
<h2>💡 DAO(Data Access Object)<h2>

</aside>

- 풀어 해석하면 Data에 직접 Access하는 객체를 의미
- 다시 말해 실제 DB에 접근하여 CRUD하는 객체
- Serviece와 DB를 연결하는 고리의 역할
- SQL을 사용(개발자가 직접 코딩)하여 DB에 접근한 후 적절한 CRUD API를 제공
<br>
<aside>
<h2>💡 DTO(Data Transfer Object)<h2>

</aside>

- 계층 간 데이터 교환을 위해 Data를 변형하여 사용하는 객체임(Java Beans)
- DB에서 데이터를 얻어 Service나 Controller 등으로 보낼 떄 사용하는 객체
- 즉 DB의 데이터가 Presentation Logic Tier로 넘어오게 될 때는 DTO의 모습으로 바뀌어 오고 가는 것
- 특징
    - 로직을 가지고 있지 않으며, 순수하게 getter/setter로만 이루어져있는 객체임
    - 하지만 DB에서 꺼낸 값을 임의로 변경할 필요가 없기 때문에 DTO클래스에는 setter가 없음(대신 생성자에서 값을 할당()
    
- 언제 씀?
    - 모든 회원 정보를 불러와야 한다고 가정
    - User Table에는 회원의 이름, 성별, 나이, 핸드폰번호, 아이디, 비밀번호 등 많은 정보들이 존재
    - 하지만 나는 이름, 성별, 나이만 필요할 때
    - User Table에 모든 데이터가 필요하지 않은 지금, Entity로 만들어 둔 class를 사용하기에는 보안 상의 문제 필요없는 값을 가지고 있다는 점에서 좋지 않음
    - 이런 경우 이름, 성별, 나이만 담는 DTO를 만들어 사용함
- Request와 Respose용 DTO는 View를 위한 클래스
    - 자주 변경이 필요한 클래스
    - Presentation Model
    - toEntity()메서드를 통해서 DTO에서 필요한 부분을 이용하여 Entity로 만듬
    - 또한 Controller Layer에서 Response DTO형태로 Client에 전달
<br>
<aside>
<h2>💡 VO(Value Object)<h2>

</aside>

- DTO와 동일한 개념이지만, Read Only의 속성을 지니고 있음

<br>
<aside>
<h2>💡 Entity<h2>

</aside>

- 실제 DB Table과 연결될 클래스임
- @Table, @ID, @Column등의 어노테이션이 사용
