<aside>
<h2>๐ก ๋์  ๊ณํ๋ฒ(Dynamic Programming)</h2>

</aside>

- ๋์  ๊ณํ๋ฒ์ด๋ ํน์  ๋ฒ์๊น์ง์ ์ต์ ํด(์์ ๋ฌธ์ )๋ฅผ ๊ตฌํ๊ธฐ ์ํ์ฌ ๋ค๋ฅธ ๋ฒ์๊น์ง์ ์ต์ ํด(ํ์ ๋ฌธ์ )๋ฅผ ์ด์ฉํ์ฌ ํจ์จ์ ์ผ๋ก ํด๋ฅผ ๊ตฌํ๋ ์๊ณ ๋ฆฌ์ฆ ์ค๊ณ ๊ธฐ๋ฒ์ด๋ค
- ์ฝ๊ฒ ๋งํด, ์ด์ ์ ๊ตฌํ ๊ฐ์ ๊ธฐ๋ฐ์ผ๋ก ๊ท์น์ฑ์ ํ์ํ์ฌ ๋ค์ ๊ฐ์ ๊ตฌํ๋ ๊ฒ์ด๋ผ๊ณ  ์๊ฐํ๋ฉด ๋๋ค
- ์๊ณ ๋ฆฌ์ฆ ์ค๊ณ ๊ธฐ๋ฒ(ํจ๋ฌ๋ค์)์ค ํ๋์ด๋ค
- ํ์ ๋ฌธ์ ์ ์ต์ ํด๋ฅผ ์ ์ ํ ์ฌ์ฉํ์ฌ ์์ ๋ฌธ์ ๋ฅผ ํด๊ฒฐํจ์ผ๋ก์จ ๋ถํ์ํ ๊ณ์ฐ์ ์ค์ผ ์ ์๋ค
- ์ด๋ค ๋ฌธ์ ๋ฅผ ํด๊ฒฐํ  ๋ ๊ธฐ๋ณธ์ ์ธ ๋ฐฉ๋ฒ์ ๋ชจ๋  ๊ฒฝ์ฐ์ ์๋ฅผ ๊ณ ๋ คํ๋ ๊ฒ(์์  ํ์)์ด๋ค ์ด๋ค ๋ฌธ์ ๋ฅผ ํด๊ฒฐํ  ๋ ๊ทธ ๋ฌธ์ ์ ๋ํ ๋ชจ๋  ๊ฒฝ์ฐ์ ์๋ฅผ ๊ณ ๋ คํ  ์ ์๋ ์ค๊ณ๊ฐ ๊ฐ๋ฅํ๋ค๋ฉด ๊ทธ ๋ฌธ์ ๋ ์๊ฐ๊ณผ ์์์ด ๋งค์ฐ ๋ง์ด ๋ค์ง๋ ๋ชฐ๋ผ๋ ์ธ์  ๊ฐ ๋ฐ๋์ ์ ํํ ๊ฒฐ๊ณผ๋ฅผ ๋์ถํ  ๊ฒ์ด๋ค
- ๋ค๋ง ์๊ณต๊ฐ์  ์์์ ํ๊ณ๋ก ์ธํ์ฌ ๋ถํ  ์ ๋ณต, ๊ทธ๋ฆฌ๋, ๋ฐฑํธ๋ํน ๋ฑ๊ณผ ๊ฐ์ ์๊ณ ๋ฆฌ์ฆ ์ค๊ณ ๊ธฐ๋ฒ์ด ๋ฑ์ฅํ ๊ฒ์ด๊ณ  ๋์ ๊ณํ๋ฒ ์ญ์ ๊ทธ๋ฌํ ํ๊ณ๋ฅผ ์ํด ์ค๊ณ๋ ์๊ณ ๋ฆฌ์ฆ ํจ๋ฌ๋ค์์ธ ๊ฒ์ด๋ค
- ๋์ ๊ณํ๋ฒ์ด๋ผ๋ ์ด๋ฆ์ ๋ฑํ ํด๋น ์๊ณ ๋ฆฌ์ฆ์ ํจ๋ฌ๋ค์์ ์ดํดํ๋ ๋ฐ ์ง๊ด์ ์ด์ง ์์ ํธ์ด๋ค

<br>
<aside>
<h2>๐ก ์ ์ฉ ๊ฐ๋ฅํ ๋ฌธ์ </h2>

</aside>

- ๋์  ๊ณํ๋ฒ์ ์๋ ๋ ์กฐ๊ฑด์ ๋ง์กฑํ๋ ๊ฒฝ์ฐ ํด๋น ํจ๋ฌ๋ค์์ ์ ์ฉํ์ฌ ๋ฌธ์ ๋ฅผ ํด๊ฒฐํ๋๋ฐ ์ ์ฉํ๋ค๊ณ  ์๋ ค์ ธ ์๋ค
- ์ต์  ๋ถ๋ถ ๋ฌธ์ ๊ตฌ์กฐ(Optimal Substructure)
    - ์ฝ๊ฒ ๋งํด ์์ ์ ์ํ ๋ฐ์ ๊ฐ์ด ์ด์ ์ ๊ตฌํ ์ต์ ํด(๋ถ๋ถ ๋ฌธ์ )๋ฅผ ๋ฐํ์ผ๋ก ๋ค์ ๋ฌธ์ ์ ์ต์ ํด(์ ์ฒด ๋ฌธ์ )๋ฅผ ๊ตฌํ  ์ ์๋ ๊ตฌ์กฐ์ฌ์ผ ํ๋ค๋ ๊ฒ์ด๋ค
    - ๋ค์ ๋งํด ๋ถ๋ถ ๋ฌธ์ ๊ฐ ์ ์ฒด ๋ฌธ์ ์ ์ต์ ํด๋ผ๋ ๋ณด์ฅ์ด ์๋ ๊ตฌ์กฐ๋ฅผ ์ต์  ๋ถ๋ถ ๋ฌธ์  ๊ตฌ์กฐ๋ผ๊ณ  ์๊ฐํ๋ฉด ๋๋ค.
    - ๋์  ๊ณํ๋ฒ์ ์ ํ์ฉํ๋ ค๋ฉด ๋ถ๋ถ๋ฌธ์ ๋ฅผ ์ด๋ป๊ฒ ์ค์ ํด์ผ ์ต์  ๋ถ๋ถ ๋ฌธ์  ๊ตฌ์กฐ๋ฅผ ๊ฐ๋์ง ์ ํ์ํด์ผ ํจ์ ์ ์ ์๋ค
- ์ค๋ณต ๋ถ๋ถ ๋ฌธ์  ๊ตฌ์กฐ(Overlapping Subproblems)
    - ๋ง ๊ทธ๋๋ก ๋ถ๋ถ ๋ฌธ์ ๋ค์ด ๋ฐ๋ณต๋๋ ๊ฒฝํฅ์ด ์กด์ฌํ๋ค๋ ๊ฒ์ ์๋ฏธํ๋ค
    - ์ฝ๊ฒ ๋งํด์ ๋ถ๋ถ ๋ฌธ์ ๋ฅผ ๋ถํ ํด๊ฐ๋ ๊ณผ์ ์์ ๊ทธ ๊ฐ ์์ ๋ฌธ์ ์ ํ์ ๋ฌธ์ ์ ๊ด๊ณ๊ฐ ๋ฐ๋ณต๋๋ ๊ฒฝํฅ์ด ์กด์ฌํ๋ค๋ ๊ฒ์ ์๋ฏธํ๋ค
    - ์ ์ฒด ๋ฌธ์ ๋ฅผ ๋ถ๋ถ ๋ฌธ์ ๋ก ๋๋๊ณ , ๊ทธ ๋ถ๋ถ ๋ฌธ์ ๋ฅผ ์์ ๋ฌธ์ ๋ถํฐ ํด๊ฒฐํด ๋์๊ฐ๊ณ , ๊ฐ ๋จ๊ณ์์ ๊ตฌํ ํด๋ฅผ ๋ค์ ๋ฌธ์ ์์ ์ฌ์ฌ์ฉํจ์ผ๋ก์จ ์ ์ฒด ๋ฌธ์ ๋ฅผ ํด๊ฒฐํ๋ค๋ ๊ฒ์ด๋ค.
    
<br>
<aside>
<h2>๐ก vs ๋ถํ  ์ ๋ณต ํจ๋ฌ๋ค์</h2>

</aside>

- ๋์  ๊ณํ๋ฒ๊ณผ ๋ถํ  ์ ๋ณต ํจ๋ฌ๋ค์ ๋ชจ๋ ์ ์ฒด ๋ฌธ์ ๋ฅผ ๋ถ๋ถ ๋ฌธ์ ๋ก ๋๋์ด ์๊ฐํ๋ค๋ ์ ์์ ๊ทธ ์ฐจ์ด์ ์ ๋๋ผ๊ธฐ ์ด๋ ค์ธ ์ ์๋ค
- ์ด๋ฅผ ๊ตฌ๋ถํ๊ธฐ ๊ฐ์ฅ ์ข์ ๊ฒ์ ๋์  ๊ณํ๋ฒ์ ๋ถ๋ถ ๋ฌธ์  ์ฌ์ด์ ์ฐ๊ด์ฑ์ด ์กด์ฌํ๊ณ ,
- ๋ถํ  ์ ๋ณต์ ๋ถ๋ถ ๋ฌธ์  ์ฌ์ด์ ์ฐ๊ด์ฑ์ด ์กด์ฌํ์ง ์๋๋ค๋ ์ ์ ์ดํดํ๋ฉด ๋๋ค
- ์๋ฅผ ๋ค์ด ๋ณํฉ ์ ๋ ฌ์ ์๊ฐํด๋ณด์ ๋ณํฉ ์ ๋ ฌ์ ๊ฒฝ์ฐ ๋ชจ๋  ๋ฐฐ์ด์ ๊ฐ๊ฐ ๋ถํ (๋ถ๋ถ ๋ฌธ์ )ํ๊ณ  ์ต์ข์ ์ผ๋ก ๋ถํ ๋ ๋ฐฐ์ด๋ถํฐ ๊ฐ ๋ฐฐ์ด์ ํฉ์น๋ฉฐ ์ ๋ ฌํ๋ ๊ณผ์ ์ ๋ฐ๋ณต(๋จ์ํ ๋ถ๋ถ ๋ฌธ์ ๋ฅผ ํฐ ๋ฌธ์ ๋ก ๊ฒฐํฉํ๋ฉฐ ํด๊ฒฐ)ํ๋ ๊ฒ์ด๋ค. ์ฆ ๋ถ๋ถ ๋ฌธ์  ์ฌ์ด์ ๋ฑํ ๋ณ ์ฐ๊ด์ฑ์ด ์์์ ์ ์ ์๋ค.
<br>
<aside>
<h2>๐ก ๊ตฌํ ๋ฐฉ์</h2>

</aside>

- ๋์  ๊ณํ๋ฒ์ ํน์ฑ์ Top-Down ๋ฐฉ์๊ณผ Bottom-Up๋ฐฉ์์ผ๋ก ๊ตฌํ์ด ๊ฐ๋ฅํ๋ค
- ์ฌ์ค ์ด๋ค ๋ฌธ์ ๋ฅผ ํธ๋๋์ ๋ฐ๋ผ์ t-d ๋ฐฉ์์ผ๋ก ๊ตฌํํ๋  b-u๋ฐฉ์์ผ๋ก ๊ตฌํํ๋  ๊ฐ ๋ฐฉ์์ด ์๋์ ์ผ๋ก ์ฐ์๋ฅผ ๊ฐ์ง๋ ์ฅ๋จ์ ์ ๋ชํํ์ง ์๋ค๊ณ  ํ๋ค.
- Top-down
    - ์ ์ฒด ๋ฌธ์ ๋ถํฐ ์์ํ์ฌ ๊ฐ์ฅ ์์ ๋ฌธ์ (๊ธฐ์  ๋ฌธ์ )๊น์ง ํธ์ถํ ๋ค, ์์ ๋ฌธ์ ์์ ํด๊ฒฐํ ๊ฐ์ ์ ์ฅ ๋ฐ ๊ธฐ์ตํ๋ฉด์ ํด๋น ๊ฒฐ๊ณผ ๊ฐ์ ์ฌํ์ฉํ๋ฉด์ ๋ฌธ์ ๋ฅผ ํด๊ฒฐํ๋ ๊ตฌํ ๋ฐฉ์์ด๋ค.
    - ์ด๋ฌํ ๋ฌธ์  ํด๊ฒฐ์ ํน์ฑ์ ์ฌ๊ท ํธ์ถ์ ์ฌ์ฉํ๋ ํน์ง์ด ์๋ค.
    - ์ฌ๊ท ํธ์ถ์ ์ฌ์ฉํ๊ธฐ ๋๋ฌธ์ Stack Overflow๋ฑ์ ๋ฌธ์ ๊ฐ ๋ฐ์ํ  ์ ์์ง๋ง, ์ ์ฒด ๋ฌธ์ ๋ถํฐ ์์ํ์ฌ ์์ ใ๋์ ๋ก ๋ด๋ ค๊ฐ๋ ์ง๊ด์ ์ธ ๊ตฌ์กฐ์ด๊ธฐ ๋๋ฌธ์ ์ดํดํ๊ธฐ ์ฌ์ด ์ฅ์ ์ด ์กด์ฌํ๋ค.
- Bottom-up
    - ๊ฐ์ฅ ์์ ๋ฌธ์ (๊ธฐ์  ๋ฌธ์ )๋ถํฐ ์์ํ์ฌ ์์ ๋ฌธ์ ๋ฅผ ํด๊ฒฐํ์ฌ ๊ทธ ๊ฐ์ ์ ์ฅํ๊ณ  ์ด ๊ฐ๋ค์ ๊ธฐ๋ฐ์ผ๋ก ๋ค์ ๋ฌธ์ ๋ฅผ ์์ฐจ์ ์ผ๋ก ํด๊ฒฐํ๋ฉฐ ์ ์ฒด ๋ฌธ์ ๊น์ง ํด๊ฒฐํ๋ ๊ตฌํ ๋ฐฉ์์ ๋งํ๋ค. ์ด๋ฌํ ๋ฌธ์  ํด๊ฒฐ์ ํน์ฑ ์ ๋ฐ๋ณต๋ฌธ์ ์ฌ์ฉํ๋ ํน์ง์ด ์๋ค.
    - ๋ฐ๋ณต๋ฌธ์ ์ฌ์ฉํ๊ธฐ ๋๋ฌธ์ Top-down ๋ฐฉ์์ ๋นํ์ฌ ํฝใน์ฑ์ด ์ข๋ค๊ณ  ์๋ ค์ ธ ์์ง๋ง ์์ ใ๋ผํ๋๋ก ๋ฌธ์  ๋ฐ ์ค๋ฒํค๋, ์ค๊ณ์ ๋ฐ๋ผ์ ์ผ๋ฐ์ผ๋ผ๊ณ  ํ๋ค.
    - ๋ํ ์ง๊ด์ ์ธ ๊ตฌ์กฐ๊ฐ ์๋๊ธฐ ๋๋ฌธ์ ๊ตฌํ์ด ์ด๋ ค์ธ ์ ์๋ ๋จ์ ์ด ์กด์ฌํ๋ค.
<br>
<aside>
<h2>๐ก ํผ๋ณด๋์น ์์ด๊ณผ DP</h2>

</aside>

- ๋จ์ ์ฌ๊ทํธ์ถ
    
    ```java
    package AlgorithmSrc;
    import java.io.*;
    public class DP {
        public static void main(String[] args) throws IOException{
            BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
            int N = Integer.parseInt(br.readLine());
    
            //n๋ฒ์งธ ํผ๋ณด๋์น ์๋ฅผ ๊ตฌํ๊ณ  ์ถ๋ ฅํ๋ผ
            System.out.println(fibonacci(N));
            br.close();
        }
        private static long fibonacci(int n){
            if(n==1||n==2){
                return 1;
            }
            //์ ํ์
            return fibonacci(n-1)+fibonacci(n-2);
        }
    }
    ```
    
    ์๊ฐ์ด ๊ต์ฅํ ์ค๋๊ฑธ๋ฆผ
    
- Top-down ๋ฐฉ์์ผ๋ก ๊ตฌํํ ํผ๋ณด๋์น ์์ด
    
    ```java
    package AlgorithmSrc;
    import java.io.*;
    public class DP_fibonacci_TopDown {
        static long[] dp;
        public static void main(String[] args) throws IOException{
            BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
            int N = Integer.parseInt(br.readLine());
            dp = new long[N+1];
            System.out.println(Fibonacci(N));
    
        }
        private static long Fibonacci(int n){
            if(n==1||n==2){
                return dp[n]=1;
            }
            if (dp[n]!=0){
                return dp[n];
            }else{
                return dp[n]=Fibonacci(n-1)+Fibonacci(n-2);
            }
        }
    }
    ```
    
- Bottom-up ๋ฐฉ์์ผ๋ก ๊ตฌํํ ํผ๋ณด๋์น ์์ด
    
    ```java
    package AlgorithmSrc;
    import java.io.*;
    public class DP_fibonacci_BottomUp {
        static long[] dp;
        public static void main(String[] args) throws IOException{
            BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
            int n = Integer.parseInt(br.readLine());
            dp=new long[n+1];
            dp[1]=1;
            dp[2]=1;
            System.out.println(Fibonacci(n));
        }
        private static long Fibonacci(int n){
            for (int i = 3; i <=n; i++) {
                dp[i]=dp[i-1]+dp[i-2];
            }
            return dp[n];
        }
    }
    ```
    
<br>
<aside>
<h2>๐ก ๋์  ๊ณํ๋ฒ ๋ฌธ์  ์ ๊ทผ ๋ฐฉ์</h2>

</aside>

1. ๋ฌธ์ ๋ฅผ ํน์ ํ ๋ถ๋ถ๋ฌธ์ ๋ก ๋๋๊ณ , ํด๋น ๋ถ๋ถ ๋ฌธ์ ์ ์ต์ ํด๋ค์ ์ ์ฅํ  dpํ์ด๋ธ์ ์ ์ํด๋ณด๊ธฐ
- ์ฝ๊ฒ ๋งํด ๋ถ๋ถ ๋ฌธ์ ๋ฅผ ๋ฌด์์ผ๋ก ๋๊ฒ์ด๊ณ , ๊ทธ๊ฑธ ์ด๋ป๊ฒ ์ ์ฅํ  ๊ฒ์ธ์ง ์๊ฐํ๋ ๋จ๊ณ

1. ๋ถ๋ถ ๋ฌธ์ ์ ๊ด๊ณ๋ฅผ ์๊ฐํ๋ฉฐ ์ ํ์์ ๋์ถ
- ์ฝ๊ฒ ๋งํด ํด๋น ๋ถ๋ถ ๋ฌธ์ ์ ๊ท์น์ฑ์ ํ์ํด๋ณด๊ณ  ์ ํ์๊ณผ ๊ธฐ์  ์กฐ๊ฑด์ ์ ์ํ๋ ๋จ๊ณ

1. ์ ํ์์ ๋ฐํ์ผ๋ก dpํ์ด๋ธ์ ๊ฐฑ์ ํ๋ฉด์ ์ต์ข์ ์ผ๋ก ์ ์ฒด ๋ฌธ์ ๋ฅผ ํด๊ฒฐ
