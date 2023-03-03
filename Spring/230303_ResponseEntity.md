<aside>
<h2>💡 도입 </h2>

</aside>

- 이번 Mini Project 기간 때 다른 팀원이 ReponseEntity를 Return으로 사용하는 코드를 보고, 잘 모르던 방식의 스타일이라 배워두면 좋을 것 같았음
- 또한 이전에 작성하던 방식은 보통 Object를 반환했기 때문에 상태코드나, 응답 메시지 등의 반환이 한 번에 이뤄지기 어려웠음
- 그러나 Response Entity는 HttpEntity를 상속 받기 때문에 좀 더 좋은 API 개발이 가능할 듯 싶어 공부하고자 함
<br>
<aside>
<h2>💡 ReponseEntity</h2>

</aside>

- ReponseEntity란 httpentity를 상속받는 결과 데이터와 HTTP 상태 코드를 직접 제어할 수 있는 클래스
- ReponseEntity에는 사용자의 HttpRequest에 대한 응답 데이터가 포함
- 또한 HTTP 아키텍쳐 형태에 맞게 Response 를 보내주는 것에도 의미가 있음
- 에러 코드와 같은 HTTP 상태 코드를 전송하고 싶은 데이터와 함께 전송할 수 있기 때문에 좀 더 세밀한 제어가 필요한 경우 사용
<br>
<aside>
<h2>💡 ResponseEntity의 구조</h2>

</aside>

- ReponseEntity는 HttpEntity를 상속받고 사용자의 응답 데이터가 포함된 클래스이기 때문에
- HttpStatus, HttpHeaders, HttpBody를 포함

![ResponseEntity.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/0a765a13-637a-4266-b240-25571be6292d/ResponseEntity.png)

- 실제 구현된 인터페이스를 보면 <바디, 헤더, 상태코드> 순의 생성자가 만들어지는 것을 볼 수 있음

<br>
<aside>
<h2>💡 Http Header와 Body의 차이점</h2>

</aside>

- http header :  요청/응답에 대한 요구사항
- http body : 그 내용
- Response header에는 웹서버가 웹브라우저에 응답하는 메세지가 들어있고,
- Reponse body에 데이터 값이 들어가있음
<br>
<aside>
<h2>💡 response header form</h2>

</aside>

- 웹 브라우저가 요청한 메시지에 대해서 status, 즉 성공했는지 여부(202, 400 등), 메시지, 그리고 요청한 응답 값들이 body에 담겨있음
    - Location : 301, 302 상태 코드일 때만 볼 수 있는 헤더로 서버의 응답이 다른 곳에 있다고 알려주면서 해당 위치(URI)를 지정
    - Server : 웹 서버의 종류 ex)nginx
    - Age : max-age 시간 내에서 얼마나 흘렀는지 초 단위로 알려주는 값
    - Referrer-policy : 서버 referrer 정책을 알려주는 값 ex) origin, no-referrer, unsafe-url
    - WWW-Authenticate : 사용자 인증이 필요한 자원을 요구할 시 서버가 제공하는 인증방식
    - Proxy-Authenticate :  요청한 서버가 프록시 서버인 경우 유저 인증을 위한 값
- 정리하면 ReponseEntity 클래스를 사용하면 결과값, 상태코드, 헤더값을 모두 프론트에 넘겨줄 수 있고, 에러코드 또한 섬세하게 설정해서 보내줄 수 있다는 장점이 있음

<br>
<aside>
<h2>💡 Example</h2>

</aside>

```java
@RestController
@RequiredArgsConstructor
public class ResponseEntityController {
	
	private final ResponseEntityService service;

	@GetMapping("/user/{id}")
	public ResponseEntity<CustomerDTO> findByid(@PathVarialbe Long id) {
		
		User user service.getUser();
		CustomerDTO customer = new CustomerDTO();

		HttpHeaders header = new HttpHeaders();
		header.setContentType(new MediaType("application", "json", Charset.forName("UTF-8")));

		customer.setStatus(StatusEnum.OK);
		customer.setData(user);
		customer.setMessage("메세지");

		return new ResponseEntity<>(customer, header, HttpStatus.OK);
	}
}
```

```java
//상태코드만 반환
@PostMapping("/post/like")
public ResponseEntity<SetLikeDTO.Response> updateLike(@RequestBody SetLikeDto,Request postLikeDto, @AuthenticationPrincipal UserDetailsImpl userDetails){
	
	Post post = postService.setPostLike(postLikeDto, userDetails.getUser());

	SetLikeDto.Response response = modelMapper.map(post, SetLikeDto.Response.class);

	return ReponseEntity.ok().build();
}

//body까지 보내줄 때
@PostMapping("/post/like")
public ResponseEntity<SetLikeDto.Response> updateLike(@RequestBody SetLikeDto.Request postLikeDto, @AuthenticationPrincipal UserDetailsImpl userDetails){
    Post post = postService.setPostLike(postLikeDto,userDetails.getUser());

    SetLikeDto.Response response = modelMapper.map(post, SetLikeDto.Response.class);

    return ResponseEntity.ok(response);
}
```
