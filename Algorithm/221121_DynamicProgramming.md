<aside>
<h2>💡 동적 계획법(Dynamic Programming)</h2>

</aside>

- 동적 계획법이란 특정 범위까지의 최적해(상위 문제)를 구하기 위하여 다른 범위까지의 최적해(하위 문제)를 이용하여 효율적으로 해를 구하는 알고리즘 설계 기법이다
- 쉽게 말해, 이전에 구한 값을 기반으로 규칙성을 파악하여 다음 값을 구하는 것이라고 생각하면 된다
- 알고리즘 설계 기법(패러다임)중 하나이다
- 하위 문제의 최적해를 적절히 사용하여 상위 문제를 해결함으로써 불필요한 계산을 줄일 수 있다
- 어떤 문제를 해결할 때 기본적인 방법은 모든 경우의 수를 고려하는 것(완전 탐색)이다 어떤 문제를 해결할 때 그 문제에 대한 모든 경우의 수를 고려할 수 있는 설계가 가능하다면 그 문제는 시간과 자원이 매우 많이 들지는 몰라도 언젠가 반드시 정확한 결과를 도출할 것이다
- 다만 시공간적 자원의 한계로 인하여 분할 정복, 그리디, 백트래킹 등과 같은 알고리즘 설계 기법이 등장한 것이고 동적계획법 역시 그러한 한계를 위해 설계된 알고리즘 패러다임인 것이다
- 동적계획법이라는 이름은 딱히 해당 알고리즘의 패러다임을 이해하는 데 직관적이지 않은 편이다

<br>
<aside>
<h2>💡 적용 가능한 문제</h2>

</aside>

- 동적 계획법은 아래 두 조건을 만족하는 경우 해당 패러다임을 적용하여 문제를 해결하는데 유용하다고 알려져 있다
- 최적 부분 문제구조(Optimal Substructure)
    - 쉽게 말해 앞서 정의한 바와 같이 이전에 구한 최적해(부분 문제)를 바탕으로 다음 문제의 최적해(전체 문제)를 구할 수 있는 구조여야 한다는 것이다
    - 다시 말해 부분 문제가 전체 문제의 최적해라는 보장이 있는 구조를 최적 부분 문제 구조라고 생각하면 된다.
    - 동적 계획법을 잘 활용하려면 부분문제를 어떻게 설정해야 최적 부분 문제 구조를 갖는지 잘 파악해야 함을 알 수 있다
- 중복 부분 문제 구조(Overlapping Subproblems)
    - 말 그대로 부분 문제들이 반복되는 경향이 존재한다는 것을 의미한다
    - 쉽게 말해서 부분 문제를 분할해가는 과정에서 그 각 상위 문제와 하위 문제의 관계가 반복되는 경향이 존재한다는 것을 의미한다
    - 전체 문제를 부분 문제로 나누고, 그 부분 문제를 작은 문제부터 해결해 나아가고, 각 단계에서 구한 해를 다음 문제에서 재사용함으로써 전체 문제를 해결한다는 것이다.
    
<br>
<aside>
<h2>💡 vs 분할 정복 패러다임</h2>

</aside>

- 동적 계획법과 분할 정복 패러다임 모두 전체 문제를 부분 문제로 나누어 생각한다는 점에서 그 차이점을 느끼기 어려울 수 있다
- 이를 구분하기 가장 좋은 것은 동적 계획법은 부분 문제 사이에 연관성이 존재하고,
- 분할 정복은 부분 문제 사이에 연관성이 존재하지 않는다는 점을 이해하면 된다
- 예를 들어 병합 정렬을 생각해보자 병합 정렬의 경우 모든 배열을 각각 분할(부분 문제)하고 최종적으로 분할된 배열부터 각 배열을 합치며 정렬하는 과정을 반복(단순히 부분 문제를 큰 문제로 결합하며 해결)하는 것이다. 즉 부분 문제 사이에 딱히 별 연관성이 없음을 알 수 있다.
<br>
<aside>
<h2>💡 구현 방식</h2>

</aside>

- 동적 계획법은 특성상 Top-Down 방식과 Bottom-Up방식으로 구현이 가능하다
- 사실 어떤 문제를 푸느냐에 따라서 t-d 방식으로 구현하든 b-u방식으로 구현하든 각 방식이 압도적으로 우위를 가지는 장단점은 명확하지 않다고 한다.
- Top-down
    - 전체 문제부터 시작하여 가장 작은 문제(기저 문제)까지 호출한 뒤, 작은 문제에서 해결한 값을 저장 및 기억하면서 해당 결과 값을 재활용하면서 문제를 해결하는 구현 방식이다.
    - 이러한 문제 해결의 특성상 재귀 호출을 사용하는 특징이 있다.
    - 재귀 호출을 사용하기 떄문에 Stack Overflow등의 문제가 발생할 수 있지만, 전체 문제부터 시작하여 작은 ㅁ누제로 내려가는 직관적인 구조이기 때문에 이해하기 쉬운 장점이 존재한다.
- Bottom-up
    - 가장 작은 문제(기저 문제)부터 시작하여 작은 문제를 해결하여 그 값을 저장하고 이 값들을 기반으로 다음 문제를 순차적으로 해결하며 전체 문제까지 해결하는 구현 방식을 말한다. 이러한 문제 해결의 특성 상 반복문을 사용하는 특징이 있다.
    - 반복문을 사용하기 때문에 Top-down 방식에 비하여 횽ㄹ성이 좋다고 알려져 있지만 앞서 ㅁ라한대로 문제 및 오버헤드, 설계에 따라서 케바케라고 한다.
    - 또한 직관적인 구조가 아니기 때문에 구현이 어려울 수 있는 단점이 존재한다.
<br>
<aside>
<h2>💡 피보나치 수열과 DP</h2>

</aside>

- 단순 재귀호출
    
    ```java
    package AlgorithmSrc;
    import java.io.*;
    public class DP {
        public static void main(String[] args) throws IOException{
            BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
            int N = Integer.parseInt(br.readLine());
    
            //n번째 피보나치 수를 구하고 출력하라
            System.out.println(fibonacci(N));
            br.close();
        }
        private static long fibonacci(int n){
            if(n==1||n==2){
                return 1;
            }
            //점화식
            return fibonacci(n-1)+fibonacci(n-2);
        }
    }
    ```
    
    시간이 굉장히 오래걸림
    
- Top-down 방식으로 구현한 피보나치 수열
    
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
    
- Bottom-up 방식으로 구현한 피보나치 수열
    
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
<h2>💡 동적 계획법 문제 접근 방식</h2>

</aside>

1. 문제를 특정한 부분문제로 나누고, 해당 부분 문제의 최적해들을 저장할 dp테이블을 정의해보기
- 쉽게 말해 부분 문제를 무엇으로 둘것이고, 그걸 어떻게 저장할 것인지 생각하는 단계

1. 부분 문제의 관계를 생각하며 점화식을 도출
- 쉽게 말해 해당 부분 문제의 규칙성을 파악해보고 점화식과 기저 조건을 정의하는 단계

1. 점화식을 바탕으로 dp테이블을 갱신하면서 최종적으로 전체 문제를 해결
