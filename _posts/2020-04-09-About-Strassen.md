---
layout: single
date: 2020-04-09 01:20:00 +0900
title: "About Strassen"
---

# About Strassen

---



## 1. 스트라센이란?

스트라센은 *인물의 이름*이다. Volker Strassen(볼커 스트라센)은 독일의 수학자로, **스트라센 알고리즘을 연구**하여 알고리즘 분석에 중요한 공헌을 한 그는 패리스 카넬라키스 상을 수상받았다.

그는 반복로그의 법칙에 대한 불변성원리는 반복 로그의 법칙의 기능적 형태를 정의하여 무작위 행보에서 규모 불변량의 형태를 보여주었다. 또한 시간 복잡도  *O(N^3)* 시간 경계보다 **빠르게 행렬 곱셈을 수행** 하는 첫 번째 알고리즘인 스트라센 알고리즘을 분석했다.

정의에 따라 *n*×*n* 크기의 두 행렬을 곱하면 O(n^3)의 시간이 소요되지만 이 알고리즘은 대략 O(n^2.807)의 시간이 소요된다.

![Volker Strassen](https://user-images.githubusercontent.com/62869982/78812858-07a78400-7a07-11ea-8f21-f6af55ffacc4.jpg)



## 2. 스트라센알고리즘

*A*와 *B*를 F에 대한 정사각행렬이라고 하자. 두 행렬의 곱 C는 다음과 같다.

![{\displaystyle \mathbf {C} =\mathbf {A} \mathbf {B} \qquad \mathbf {A} ,\mathbf {B} ,\mathbf {C} \in F^{2^{n}\times 2^{n}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/f4c680ec4a32379114e0326ba69b179881b69e8e)

만약 *A*와 *B*가 2n × 2n 꼴의 크기가 아니라면 먼저 모자라는 행과 열을 0으로 채운다. 이 경우 행렬 곱셈이 끝난 뒤 행렬에서 필요한 부분만 다시 잘라 내야 한다. 이제 *A*, *B*, *C*를 같은 크기의 정사각행렬 네 개로 나눈다.

![{\displaystyle \mathbf {A} ={\begin{bmatrix}\mathbf {A} _{1,1}&\mathbf {A} _{1,2}\\\mathbf {A} _{2,1}&\mathbf {A} _{2,2}\end{bmatrix}}{\mbox{ , }}\mathbf {B} ={\begin{bmatrix}\mathbf {B} _{1,1}&\mathbf {B} _{1,2}\\\mathbf {B} _{2,1}&\mathbf {B} _{2,2}\end{bmatrix}}{\mbox{ , }}\mathbf {C} ={\begin{bmatrix}\mathbf {C} _{1,1}&\mathbf {C} _{1,2}\\\mathbf {C} _{2,1}&\mathbf {C} _{2,2}\end{bmatrix}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/41c6337190684aff7b69f124226d6e62d79ebca5)

이 때,

![{\displaystyle \mathbf {A} _{i,j},\mathbf {B} _{i,j},\mathbf {C} _{i,j}\in F^{2^{n-1}\times 2^{n-1}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/e2948b2c6caf12770b217310b956b23abdc80380)

따라서 다음이 성립한다.

![{\displaystyle \mathbf {C} _{1,1}=\mathbf {A} _{1,1}\mathbf {B} _{1,1}+\mathbf {A} _{1,2}\mathbf {B} _{2,1}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/8d91fa79d27697a5c6551698c1a83a3d5837c57b)

![{\displaystyle \mathbf {C} _{1,2}=\mathbf {A} _{1,1}\mathbf {B} _{1,2}+\mathbf {A} _{1,2}\mathbf {B} _{2,2}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/a08bea24eec9422cda82e6e04af1d96fc6822038)

![{\displaystyle \mathbf {C} _{2,1}=\mathbf {A} _{2,1}\mathbf {B} _{1,1}+\mathbf {A} _{2,2}\mathbf {B} _{2,1}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/7adffe97db091ce8ba231352b3721bbe261985ca)

![{\displaystyle \mathbf {C} _{2,2}=\mathbf {A} _{2,1}\mathbf {B} _{1,2}+\mathbf {A} _{2,2}\mathbf {B} _{2,2}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/8b40ed74cf54465d8e54d09b8492e50689928313)

이 과정에서는 필요한 연산의 수가 줄어 들지 않는다. 여전히 *Ci,j* 행렬을 계산하려면 여덟 번의 곱셈과 네 번의 덧셈이 필요하다.

이제 다음과 같은 행렬을 정의한다.

![{\displaystyle \mathbf {M} _{1}:=(\mathbf {A} _{1,1}+\mathbf {A} _{2,2})(\mathbf {B} _{1,1}+\mathbf {B} _{2,2})}](https://wikimedia.org/api/rest_v1/media/math/render/svg/1e9e6268d824de7ad5010a32a1921452b264f7ee)

![{\displaystyle \mathbf {M} _{2}:=(\mathbf {A} _{2,1}+\mathbf {A} _{2,2})\mathbf {B} _{1,1}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/0d40beeba8019e378fa0ed4b6e549c44a140a9ec)

![{\displaystyle \mathbf {M} _{3}:=\mathbf {A} _{1,1}(\mathbf {B} _{1,2}-\mathbf {B} _{2,2})}](https://wikimedia.org/api/rest_v1/media/math/render/svg/45e8e9679d33f2c66e24bd812e1e554f95bb1571)

![{\displaystyle \mathbf {M} _{4}:=\mathbf {A} _{2,2}(\mathbf {B} _{2,1}-\mathbf {B} _{1,1})}](https://wikimedia.org/api/rest_v1/media/math/render/svg/c12df2bb70f8f09f33f1ca4b8c2d577d5850a2ee)

![{\displaystyle \mathbf {M} _{5}:=(\mathbf {A} _{1,1}+\mathbf {A} _{1,2})\mathbf {B} _{2,2}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/715adfa757b74b3ad6b4eea545c24762e4079161)

![{\displaystyle \mathbf {M} _{6}:=(\mathbf {A} _{2,1}-\mathbf {A} _{1,1})(\mathbf {B} _{1,1}+\mathbf {B} _{1,2})}](https://wikimedia.org/api/rest_v1/media/math/render/svg/30107b9c9c99494bf75f23e84b505e5921cee46e)

![{\displaystyle \mathbf {M} _{7}:=(\mathbf {A} _{1,2}-\mathbf {A} _{2,2})(\mathbf {B} _{2,1}+\mathbf {B} _{2,2})}](https://wikimedia.org/api/rest_v1/media/math/render/svg/9e93ef1c265be8be96209dde36230d56e139fc72)

![{\displaystyle \mathbf {C} _{1,1}=\mathbf {M} _{1}+\mathbf {M} _{4}-\mathbf {M} _{5}+\mathbf {M} _{7}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/26875b8ca1815e2c322c798faeecabe1d7836798)

![{\displaystyle \mathbf {C} _{1,2}=\mathbf {M} _{3}+\mathbf {M} _{5}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/e71779a8ecc64f3e1268485cf389a05cdd3e6bf8)

![{\displaystyle \mathbf {C} _{2,1}=\mathbf {M} _{2}+\mathbf {M} _{4}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/5853fa11f016df7eee4eb2a7ceb6137d3b3296de)

![{\displaystyle \mathbf {C} _{2,2}=\mathbf {M} _{1}-\mathbf {M} _{2}+\mathbf {M} _{3}+\mathbf {M} _{6}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/b7d7d4ee9e67e0c23f1a522787d4829072542dbb)

전체 곱셈을 일곱 번의 곱셈과 18번의 덧셈으로 처리할 수 있다. 큰 행렬에 대해서는 행렬의 곱셈이 덧셈보다 더 많은 시간을 필요로 하기 때문에 덧셈을 더 하는 대신 곱셈을 덜 하는 것이  더 효율적이다.

이 과정을 재귀적으로 반복할 경우 총![{\displaystyle 7\cdot n^{\log _{2}7}-6\cdot n^{2}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/586e85e6ba93daf1db18e144da90a79af278e9a9)번의 연산이 필요하다. ![{\displaystyle \log _{2}7=2.807\cdots }](https://wikimedia.org/api/rest_v1/media/math/render/svg/ce05babfc0fc45343915cfe440346e34e8442bfe)이므로 전체 수행 시간은 약 O(n^2.807)이다.

(슈트라센 알고리즘은 속도에 비해 안정성이 떨어진다.)

---

* 수학적 표현

  ![5286_1](https://user-images.githubusercontent.com/62869982/78816443-b3070780-7a0c-11ea-8303-971d77dc08f6.jpg)

* 알고리즘 표현

  ```
  void matrix_multiplication (n, A[,], B[,], C[,]) {
      int i, j, k
      for (i = 1; i <= n; i++) {
          for (j = 1; j <= n; j++) {
              C[i,j] = 0;
              for (k = 1; k <= n; k++)
                  C[i,j] = C[i,j] + A[i,k] * B[k,j];
          }
      }
  }
  ```

