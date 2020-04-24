---


layout: single
date: 2020-04-24 23:41:00 +0900
title: "Greedy Algorithm"
---

# Greedy Algorithm

### 그리디 알고리즘이란?

그리디알고리즘 이란 이름 그대로 **‘눈 앞에 보이는 최선’**을 탐욕적으로 선택하는 것을 반복하는 알고리즘 설계 패러다임 중 하나입니다. 

전체를 여러 조각으로 나눠서 각 단계마다 답의 일부를 만들어 간다는 점에서 완전 탐색과 비슷하지만, 모든 선택지를 보는 완전 탐색과 달리 탐욕 알고리즘은 지금 당장 가장 좋은 해답을 선택합니다.



---

---

### 탐욕 알고리즘의 예시 문제

**- DNA 서열 정렬**

서열 오류 또는 다른 소스와 동등한 오류로만 다른 DNA 서열을 정렬하는 경우, 그리디 알고리즘은 기존의 동적 프로그래밍 방식보다 훨씬 빠르지만 이론적으로 최적인 정렬을 생성 할 수 있습니다. 

특히 성능이 좋은 새로운 그리디 정렬 알고리즘을 소개하고 특정 동적 프로그래밍 알고리즘과 동일한 정렬을 계산하면서 적절한 데이터에서 10 배 이상 빠르게 실행하는 것을 보여줍니다. 이 알고리즘의 구현은 현재 국립 생명 공학 정보 센터에서 유전 데이터베이스를 조립하는 프로그램에서 사용됩니다.



**- 예시로 든 이유**

그리디 알고리즘을 이용한 문제들의 예시를 조사하다가 기계공학, 수학적 개념과 비롯하여 생화학적으로도 접근이 가능하다는 것을 알고 신선하고, 다른 예시들과는 달리 특이하다고 생각해서 조사하였다.

 

DNA의 단일가닥은 A, T, C, G들의 염기서열으로만 이루어져 있다.

*ex)AACAGCTTCAGTC* 

위와같은 나열을 3개로 나누어 AAA, AGA, UAG 등으로 나누어 성분을 분석하는 것을 활용하여  그리디 알고리즘으로 여러가지 문제를 만들고, 접근 할 수 있음을 알수 있다.

---

---





## 문제

DNA란 어떤 유전물질을 구성하는 분자이다. 이 DNA는 서로 다른 4가지의 뉴클레오티드로 이루어져 있다(Adenine, Thymine, Guanine, Cytosine). 우리는 어떤 DNA의 물질을 표현할 때, 이 DNA를 이루는 뉴클레오티드의 첫글자를 따서 표현한다.

 만약에 Thymine-Adenine-Adenine-Cytosine-Thymine-Guanine-Cytosine-Cytosine-Guanine-Adenine-Thymine로 이루어진 DNA가 있다고 하면, “TAACTGCCGAT”로 표현할 수 있다. 그리고 Hamming Distance란 길이가 같은 두 DNA가 있을 때, 각 위치의 뉴클오티드 문자가 다른 것의 개수이다. 만약에 “AGCAT"와 ”GGAAT"는 첫 번째 글자와 세 번째 글자가 다르므로 Hamming Distance는 2이다.

우리가 할 일은 다음과 같다. n개의 길이가 같은 DNA가 주어져 있을 때(이 DNA를 a1a2a3a4...이라고 하자) Hamming Distance의 합이 가장 작은 DNA s를 구하는 것이다. 즉, s와 a1의 Hamming Distance + s와 a2의 Hamming Distance + s와 a3의 Hamming Distance ... 의 합이 최소가 된다는 의미이다.



## 입력

첫 줄에 DNA의 수 N과 문자열의 길이 M이 주어진다. 그리고 둘째 줄부터 N+1번째 줄까지 N개의 DNA가 주어진다. N은 1,000보다 작거나 같은 자연수이고, M은 50보다 작거나 같은 자연수이다.

*ex)*

```
5 8
TATGATAC
TAAGCTAC
AAAGATCC
TGAGATAC
TAAGATGT
```

## 출력

첫째 줄에 Hamming Distance의 합이 가장 작은 DNA 를 출력하고, 둘째 줄에는 그 Hamming Distance의 합을 출력하시오. 그러한 DNA가 여러 개 있을 때에는 사전순으로 가장 앞서는 것을 출력한다.

*ex)*

```
TAAGATAC
7
```



**접근 방식:** 입력받은 **DNA 문자열 값들의 각 자리마다 제일 많이 나오는 문자를 선택하여 출력**한다.(단, **여러 문자가 최대 빈도를 동일하게 가지면 사전순으로 앞에있는 문자를 선택**한다) 이후 **해당 자리의 Hamming Distance를 계산한 뒤 최종적으로 출력할 거리 총합 변수에 더해**준다. 이 과정을 **문자열 첫 단어부터 마지막 단어까지 반복**한다.

---

---



## CODE

> import java.util*;
>
> public class Main{
>
> ​	public static void main(String args[]) {
>
> ​        Scanner sc = new Scanner(System.in);
>
> ​        int i, j, n = sc.nextInt(), m = sc.nextInt(), max = 0, hd = 0;
>
> ​        String []dna = new String[n];
>
> ​        for(i=0;i<n;i++) dna[i] = sc.next();
>
> ​        for(i=0;i<m;i++){
>
> ​        	int a=0,t=0,g=0,c=0;
>
> ​        	for(j=0;j<n;j++){
>
> ​        		switch(dna[j].charAt(i)){
>
> ​        		case 'A' : a++; break;
>
> ​        		case 'T' : t++; break;
>
> ​        		case 'G' : g++; break;
>
> ​        		case 'C' : c++; break;
>
> ​        		}
>
> ​        	}
>
> ​        	max = Math.max(a>c?a:c, g>t?g:t);
>
> ​        	hd += (n-max);
>
> ​        	System.out.print(toChar(a,t,g,c,max));
>
> ​        }
>
> ​        System.out.println("\n"+hd);
>
> ​        sc.close();
>
> ​    }
>
> ​    private static char toChar(int a, int t, int g, int c, int max){
>
> ​    	if(max==a) return 'A';
>
> ​    	else if(max==c) return 'C';
>
> ​    	else if(max==g) return 'G';
>
> ​    	else return 'T';
>
> ​    }
>
>  }