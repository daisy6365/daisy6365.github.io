# daisy6365.github.io

자바 버전의 역사 
 === 
 
## 차례 
* 자바란? 
  * 자바 
  * 자바의 장점 
* 자바 버전과 역사 
  * 초기 자바 ~ JDK 1.0 
  * JDK 1.1 
  * JDK 1.2 
  * JDK 1.3 
  * JDK 1.4 
  * JDK 1.5 
  * JDK 1.6 
  * JDK 1.7 
  * JDK 1.8 
  * JDK 1.9 
  
  --- 
  
  ### 자바란? 
#### 자바 
**Java**는 1991년 썬 마이크로사의 제임스 고슬링과 다른 연구진들이 처음 개발한 객체 지향 프로그래밍 언어입니다. 당시 가장 많이 사용했던 프로그래밍 언어는 C와 C++이였습니다. 하지만 가전제품이나 휴대용 장치 등에 사용하는 소프트웨어를 만들기 위해서는 독립적으로 작동하는 안정된 프로그래밍 언어가 필요했습니다. 그렇게 **“한 번 작성하면, 어디서든 돌아간다.(Write once, run anywhere)”** 라는 슬로건을 가지고 1995년 1.0 Java가 공개되었습니다. 

#### 자바의 장점 
**1. 플랫폼에 영향을 받지 않는다.** 
예를 들어 C언어 같은 경우 윈도우에서 개발을 하고 컴파일을 하면 .exe라는 파일로 만들어진다. 이는 윈도우에서 실행되는 ‘실행 파일’ 이다. 따라서 리눅스 운영체제에 맞지 않아 리눅스에서는 돌리지 못한다. 리눅스 운영체제에서 돌리려면 리눅스 운영체제에 맞는 실행 파일을 새로 만들어야 한다. 하지만 Java는 슬로건에 맞게 한번 작성한 코드를 자바 가상머신(JVM)만 있다면 어디서든 돌릴 수 있다. 

**2. 객체 지향 언어여서 유지보수가 쉽다.** 
객체 지향 프로그래밍(OOP)은 C언어와 같이 절차지향과 다르게 여러 객체가 협력하여 프로그램을 구현하는 것이다. 따라서 공통으로 사용하는 부분을 수정하지 않고도 프로그램에 새 기능을 쉽게 추가할 수 있다. 따라서 유지보수가 쉽고 확장성이 좋다. 

**3. 프로그램이 안정적입니다.** 
Java는 C, C++에서 제공하는 문법인 포인터를 사용하지 않는다. 따라서 메모리를 직접 제어할 수 없다. 또한, 동적 메모리 수거를 프로그래머가 하지 않고 가비지 컬렉터(Garbage Collector)를 이용하여 메모리를 효율적으로 관리할 수 있다. 

##### *이런 장점을 가진 자바는 다양한 프로그램을 개발할 수 있다.* 
--- 

### 자바 버전과 역사 

**1. 초기 자바 ~ JDK 1.0 ** 
- 1991년, OAK 발표: GE사의 요청으로, 썬마이크로 시스템즈에서 C++의 단점을 극복하고자 만든 언어. 메모리 할당/해제의 어려움과 다중상속으로 인한 실수유발을 극복하려고 함.
- 1996년, JDK 1.0발표 :  언어 이름을 자바라 바꾸고, Java Virtual Machine 1.0을 발표했다. Java Applet도 이때 처음 도입.

**2. JDK 1.1** 
- 1997년 : RMI, JDBC, reflection, JIT,Inner Class 개념이 포함

**3. JDK 1.2** 
- 1998년 Java SE 1.2, ME 1.2, EE 1.2 발표 
- 자바를 세가지 버전으로 나눴다. Swing이 SE에 포함, Corba IDL(이종기기간 함수호출 스펙), Collection Framework 포함

**4. JDK 1.3** 
- 2000년도에 발표 
- HotSpot(Sun에서 만든 JIT구현), JNDI(디렉토리랑 이름으로 원하는 서비스찾는것) 포함

**5. JDK 1.4** 
- 2002년도에 발표 
- JCP(Java Community Process)에 의해서 오픈소스 정책으로 자바가 관리되기 시작한 버전.
- Java 2 Security 모델의 확립(Sandbox)
- Java Web Start포함 (Java Applet이 브라우저에서 돌아가는 것과 다르게, 외부 sandbox에서 동작)
- Language: assert 도입
- API :  Regular Expression, Assert keyword, Security 2 version(현재 security model), Non Blocking IO(NIO)

**6. JDK 1.5** 
- 2004년에 발표 
- 기능적으로 가장 많은 변화가 생긴버전 (Generics가 가장 대표적)
- LanguageI: Generics , annotation, auto boxing, enum,vararg ,foreach, static imports 도입
- API : java.util.concurrent API, scanner class

**7. JDK 1.6** 
- 2006년도에 발표 
- 기능에 별 차이 없슴 - 보안, 성능강화 주력. 
- JVM/Swing에 있어 많은 Performance 향상(synchronization, compiler, GC,start-up time)
- G1(Garbage First) GC도입.

**8. JDK 1.7** 
- 2011에 발표  
- JVM : Dynamic Language support (invokedynamic - new byte operation)
- Language : Switch에서 String, try-resource, generics에서 타입추론, 숫자에서 underscore사용
- API:Concurrency 강화, NIO 강화, sort강화, crypto강화, GPU강화, 
- JavaFX가 기본으로 포함
- 안정적인 ARM지원

**9. JDK 1.8** 
- 2014에 발표
- 오라클로 인수된 후 첫번째 버전
-  JDK 1.5이후 가장 큰 언어적 변화(Lambda및 함수형프로그래밍,default method)이며 러닝커브가 큼.
- JEP에 의해서 새로운 기능들이 발의되기 시작.
- Language : Lambda expression, Default Method Interface, functional programming for MapReduce style 지원, default method이용한 다중상속지원,메소드 참조
- API : Nashorn (JS엔진), new Date and Time API, stream api,Collection에 대한 함수형화 (Interface에 default가 생김으로서 가능)
- 병철처리에 접합한 구조로 진화

**10. JDK 1.9** 
- 2016년도 발표
- Modular System (Jigsaw)지원예정
- Money API지원예정
- Java Shell지원예정
- 변수에 대한 타입 추론 지원예정(var,val)
- OpenCL이용한 자동화된 병렬 프로그래밍 지원예정
- value 타입 지원예정
