# Baekjoon Online Judge

## algorithm practice

## 단계별 문제풀기

## 8. 기본 수학1

Java / Python
<br>

### 9. Fly me to the Alpha Centauri
[1011번](https://www.acmicpc.net/problem/1011) 

> 거리에 따른 장치 사용 횟수를 출력하는 문제
![](https://images.velog.io/images/jini_eun/post/8e2d4d90-1d6c-48ea-9da5-d2a52ca54bcd/image.png)
>>우현이는 어린 시절, 지구 외의 다른 행성에서도 인류들이 살아갈 수 있는 미래가 오리라 믿었다. 그리고 그가 지구라는 세상에 발을 내려 놓은 지 23년이 지난 지금, 세계 최연소 ASNA 우주 비행사가 되어 새로운 세계에 발을 내려 놓는 영광의 순간을 기다리고 있다.<br>
그가 탑승하게 될 우주선은 Alpha Centauri라는 새로운 인류의 보금자리를 개척하기 위한 대규모 생활 유지 시스템을 탑재하고 있기 때문에, 그 크기와 질량이 엄청난 이유로 최신기술력을 총 동원하여 개발한 공간이동 장치를 탑재하였다. 하지만 이 공간이동 장치는 이동 거리를 급격하게 늘릴 경우 기계에 심각한 결함이 발생하는 단점이 있어서, 이전 작동시기에 k광년을 이동하였을 때는 k-1 , k 혹은 k+1 광년만을 다시 이동할 수 있다. 예를 들어, 이 장치를 처음 작동시킬 경우 -1 , 0 , 1 광년을 이론상 이동할 수 있으나 사실상 음수 혹은 0 거리만큼의 이동은 의미가 없으므로 1 광년을 이동할 수 있으며, 그 다음에는 0 , 1 , 2 광년을 이동할 수 있는 것이다. ( 여기서 다시 2광년을 이동한다면 다음 시기엔 1, 2, 3 광년을 이동할 수 있다. )
김우현은 공간이동 장치 작동시의 에너지 소모가 크다는 점을 잘 알고 있기 때문에 x지점에서 y지점을 향해 최소한의 작동 횟수로 이동하려 한다. 하지만 y지점에 도착해서도 공간 이동장치의 안전성을 위하여 y지점에 도착하기 바로 직전의 이동거리는 반드시 1광년으로 하려 한다. <br>
김우현을 위해 x지점부터 정확히 y지점으로 이동하는데 필요한 공간 이동 장치 작동 횟수의 최솟값을 구하는 프로그램을 작성하라.

> 규칙 찾기
![](https://images.velog.io/images/jini_eun/post/9f032d2d-06aa-4e60-8cb6-c9df78862357/image.png)

<br>

- Java

```java
import java.util.Scanner;
 
public class Main {
	public static void main(String[] args) {
    
		Scanner sc = new Scanner(System.in);
 
		int T = sc.nextInt();	
		
		for(int i = 0; i < T; i++) {
        
			int X = sc.nextInt();
			int Y = sc.nextInt();
			
			int distance = Y - X;
			
			int max = (int)Math.sqrt(distance);	
            
			if(max == Math.sqrt(distance)) {
				System.out.println(max * 2 - 1);
			}
			else if(distance <= max * max + max) {
				System.out.println(max * 2);
			}
			else {
				System.out.println(max * 2 + 1);
			}	
		}
	}
}
``` 

<br>

- Python

```python
import math

T = int(input())

for _ in range(T):
    x, y = map(int,input().split())
    distance = int(y - x)
    if distance <= 3:
        print(distance)
    else:
        cnt = int(math.sqrt(distance))
        if distance == cnt ** 2:
            print(2*cnt-1)
        elif cnt ** 2 < distance <= cnt ** 2 + cnt:
            print(2*cnt)
        else:
            print(2*cnt+1)
```

<br><br>

---

<br>


> 오늘은 기본 수학1 예제였습니다!