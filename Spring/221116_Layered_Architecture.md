<aside>
<h2>💡 **Presentation Layer**<h2>

</aside>

- 사용자와 가장 가까운 계층
- 사용자와 상호작용을 함
- SpringMVC 객체를 말하며, 프론트 컨트롤러(Dispatcher Servlet), 모델, 뷰, 컨트롤러를 의미함
<br>
<aside>
<h2>💡 **Business Layer(Service Layer)**<h2>

</aside>

- 실제 비즈니스 로직을 구현하는 컴포넌트로 트랜젝션/기능을 수행하는 레이어
- 컨트롤러(presentation layer)에서 요청을 보내면, DAO(data access layer)를 통해 실제 비즈니스 로직을 수행함
- 비즈니스 로직??????
    
    유저의 눈에는 보이지 않지만, 유저가 바라는 결과물을 도출하기 위해 올바르게 짜여진 로직
    
<br>
<aside>
<h2>💡 **Data Access Layer(Repository Layer)**<h2>

</aside>

- 데이터베이스에 연동되어 데이터의 저장과 조회를 담당
- DB에 값을 저장하거나 가져오기 위해 JDBC/JPA/Mybatis 등을 사용
<br>
<aside>
<h2>💡 **Layered Architecture Process**<h2>

</aside>

1. Client가 요청을 보내면 먼저 Presentation Layer에서 dispatcherServlet이 요청을 받고 handdlerMapping을 통해 Controller에 요청이 무엇인지 알리고, Business Layer에 요구함

1-1. 이 때 넘겨야 할 데이터가 있다면, Domain Object에 저장

2. Business Layer는 Presentation Layer와 Interface를 통해 통신하며 Client 요청을 적절히 처리한 후 데이터베이스에 데이터를 저장하거나 데이터를 꺼내기 위해 Data Access Layer에 요청

2-1. 이 때 비즈니스 로직을 수행하기 위해 데이터가 필요하면 Domain Object에서 가져오고, Data Access Layer에 넘겨줄 데이터가 있으면 Domain Object에 담는다

3. Data Access Layer 역시 Business Layer와 Interface를 통해서 통신하며, Business Layer의 요청을 처리함

3-1. 이 때 데이터베이스에 저장하기 위해 필요한 데이터를 Domain Object에서 가져오고, 데이터베이스에서 데이터를 가져와 반환할 데이터가 있다면 Domain Object에 저장

4. 모든 처리가 끝나면 Controller는 Client 요청이 처리된 데이터와 사용할 View 정보를 Domain Object에서 가져와서 ModelAndView에 담는다. 그리고 ModelAndView 객체를 DispatcherServlet에 넘긴다
5. ModelAndView 객체가 DispatcherServlet에 전달되면, DispatcherServlet은 [ViewResolver](https://www.notion.so/ViewResolver-02f489f828f84b829389b9e24d1943d7)를 통해서 View를 선택하고 Client에게 요청이 처리된 데이터를 화면에 출력
