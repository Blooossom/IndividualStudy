<aside>
<h2>๐ก ๋์ </h2>

</aside>

- ์ด๋ฒ Mini Project ๊ธฐ๊ฐ ๋ ๋ค๋ฅธ ํ์์ด ReponseEntity๋ฅผ Return์ผ๋ก ์ฌ์ฉํ๋ ์ฝ๋๋ฅผ ๋ณด๊ณ , ์ ๋ชจ๋ฅด๋ ๋ฐฉ์์ ์คํ์ผ์ด๋ผ ๋ฐฐ์๋๋ฉด ์ข์ ๊ฒ ๊ฐ์์
- ๋ํ ์ด์ ์ ์์ฑํ๋ ๋ฐฉ์์ ๋ณดํต Object๋ฅผ ๋ฐํํ๊ธฐ ๋๋ฌธ์ ์ํ์ฝ๋๋, ์๋ต ๋ฉ์์ง ๋ฑ์ ๋ฐํ์ด ํ ๋ฒ์ ์ด๋ค์ง๊ธฐ ์ด๋ ค์ ์
- ๊ทธ๋ฌ๋ Response Entity๋ HttpEntity๋ฅผ ์์ ๋ฐ๊ธฐ ๋๋ฌธ์ ์ข ๋ ์ข์ API ๊ฐ๋ฐ์ด ๊ฐ๋ฅํ  ๋ฏ ์ถ์ด ๊ณต๋ถํ๊ณ ์ ํจ
<br>
<aside>
<h2>๐ก ReponseEntity</h2>

</aside>

- ReponseEntity๋ httpentity๋ฅผ ์์๋ฐ๋ ๊ฒฐ๊ณผ ๋ฐ์ดํฐ์ HTTP ์ํ ์ฝ๋๋ฅผ ์ง์  ์ ์ดํ  ์ ์๋ ํด๋์ค
- ReponseEntity์๋ ์ฌ์ฉ์์ HttpRequest์ ๋ํ ์๋ต ๋ฐ์ดํฐ๊ฐ ํฌํจ
- ๋ํ HTTP ์ํคํ์ณ ํํ์ ๋ง๊ฒ Response ๋ฅผ ๋ณด๋ด์ฃผ๋ ๊ฒ์๋ ์๋ฏธ๊ฐ ์์
- ์๋ฌ ์ฝ๋์ ๊ฐ์ HTTP ์ํ ์ฝ๋๋ฅผ ์ ์กํ๊ณ  ์ถ์ ๋ฐ์ดํฐ์ ํจ๊ป ์ ์กํ  ์ ์๊ธฐ ๋๋ฌธ์ ์ข ๋ ์ธ๋ฐํ ์ ์ด๊ฐ ํ์ํ ๊ฒฝ์ฐ ์ฌ์ฉ
<br>
<aside>
<h2>๐ก ResponseEntity์ ๊ตฌ์กฐ</h2>

</aside>

- ReponseEntity๋ HttpEntity๋ฅผ ์์๋ฐ๊ณ  ์ฌ์ฉ์์ ์๋ต ๋ฐ์ดํฐ๊ฐ ํฌํจ๋ ํด๋์ค์ด๊ธฐ ๋๋ฌธ์
- HttpStatus, HttpHeaders, HttpBody๋ฅผ ํฌํจ

![ResponseEntity.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/0a765a13-637a-4266-b240-25571be6292d/ResponseEntity.png)

- ์ค์  ๊ตฌํ๋ ์ธํฐํ์ด์ค๋ฅผ ๋ณด๋ฉด <๋ฐ๋, ํค๋, ์ํ์ฝ๋> ์์ ์์ฑ์๊ฐ ๋ง๋ค์ด์ง๋ ๊ฒ์ ๋ณผ ์ ์์

<br>
<aside>
<h2>๐ก Http Header์ Body์ ์ฐจ์ด์ </h2>

</aside>

- http header :  ์์ฒญ/์๋ต์ ๋ํ ์๊ตฌ์ฌํญ
- http body : ๊ทธ ๋ด์ฉ
- Response header์๋ ์น์๋ฒ๊ฐ ์น๋ธ๋ผ์ฐ์ ์ ์๋ตํ๋ ๋ฉ์ธ์ง๊ฐ ๋ค์ด์๊ณ ,
- Reponse body์ ๋ฐ์ดํฐ ๊ฐ์ด ๋ค์ด๊ฐ์์
<br>
<aside>
<h2>๐ก response header form</h2>

</aside>

- ์น ๋ธ๋ผ์ฐ์ ๊ฐ ์์ฒญํ ๋ฉ์์ง์ ๋ํด์ status, ์ฆ ์ฑ๊ณตํ๋์ง ์ฌ๋ถ(202, 400 ๋ฑ), ๋ฉ์์ง, ๊ทธ๋ฆฌ๊ณ  ์์ฒญํ ์๋ต ๊ฐ๋ค์ด body์ ๋ด๊ฒจ์์
    - Location : 301, 302 ์ํ ์ฝ๋์ผ ๋๋ง ๋ณผ ์ ์๋ ํค๋๋ก ์๋ฒ์ ์๋ต์ด ๋ค๋ฅธ ๊ณณ์ ์๋ค๊ณ  ์๋ ค์ฃผ๋ฉด์ ํด๋น ์์น(URI)๋ฅผ ์ง์ 
    - Server : ์น ์๋ฒ์ ์ข๋ฅ ex)nginx
    - Age : max-age ์๊ฐ ๋ด์์ ์ผ๋ง๋ ํ๋ ๋์ง ์ด ๋จ์๋ก ์๋ ค์ฃผ๋ ๊ฐ
    - Referrer-policy : ์๋ฒ referrer ์ ์ฑ์ ์๋ ค์ฃผ๋ ๊ฐ ex) origin, no-referrer, unsafe-url
    - WWW-Authenticate : ์ฌ์ฉ์ ์ธ์ฆ์ด ํ์ํ ์์์ ์๊ตฌํ  ์ ์๋ฒ๊ฐ ์ ๊ณตํ๋ ์ธ์ฆ๋ฐฉ์
    - Proxy-Authenticate :  ์์ฒญํ ์๋ฒ๊ฐ ํ๋ก์ ์๋ฒ์ธ ๊ฒฝ์ฐ ์ ์  ์ธ์ฆ์ ์ํ ๊ฐ
- ์ ๋ฆฌํ๋ฉด ReponseEntity ํด๋์ค๋ฅผ ์ฌ์ฉํ๋ฉด ๊ฒฐ๊ณผ๊ฐ, ์ํ์ฝ๋, ํค๋๊ฐ์ ๋ชจ๋ ํ๋ก ํธ์ ๋๊ฒจ์ค ์ ์๊ณ , ์๋ฌ์ฝ๋ ๋ํ ์ฌ์ธํ๊ฒ ์ค์ ํด์ ๋ณด๋ด์ค ์ ์๋ค๋ ์ฅ์ ์ด ์์

<br>
<aside>
<h2>๐ก Example</h2>

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
		customer.setMessage("๋ฉ์ธ์ง");

		return new ResponseEntity<>(customer, header, HttpStatus.OK);
	}
}
```

```java
//์ํ์ฝ๋๋ง ๋ฐํ
@PostMapping("/post/like")
public ResponseEntity<SetLikeDTO.Response> updateLike(@RequestBody SetLikeDto,Request postLikeDto, @AuthenticationPrincipal UserDetailsImpl userDetails){
	
	Post post = postService.setPostLike(postLikeDto, userDetails.getUser());

	SetLikeDto.Response response = modelMapper.map(post, SetLikeDto.Response.class);

	return ReponseEntity.ok().build();
}

//body๊น์ง ๋ณด๋ด์ค ๋
@PostMapping("/post/like")
public ResponseEntity<SetLikeDto.Response> updateLike(@RequestBody SetLikeDto.Request postLikeDto, @AuthenticationPrincipal UserDetailsImpl userDetails){
    Post post = postService.setPostLike(postLikeDto,userDetails.getUser());

    SetLikeDto.Response response = modelMapper.map(post, SetLikeDto.Response.class);

    return ResponseEntity.ok(response);
}
```
