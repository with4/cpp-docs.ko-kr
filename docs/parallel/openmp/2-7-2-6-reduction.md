---
title: "2.7.2.6 감소 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: e7630a15-2978-4dbe-a29b-3a46371a0151
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 684067eae668398e71ca4ace0cc136e3210e0dbf
ms.sourcegitcommit: 9239c52c05e5cd19b6a72005372179587a47a8e4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/16/2018
---
# <a name="2726-reduction"></a>2.7.2.6 reduction

이 절에 표시 되는 스칼라 변수에서 감소 수행 *변수 목록*, 연산자와 함께 *op*합니다. 구문은 `reduction` 절은 다음과 같습니다.

> reduction(*op*: *variable-list*)

다음 형식 중 하나가 지정 된 문에 대 한 감소 일반적으로 지정 됩니다.

> *x* = *x* *op* *expr*  
> *x* *binop* = *expr*  
> *x* = *expr* *op* *x* 빼기) (제외  
> *x*++  
> ++*x*  
> *x*--  
> --*x*  

다음은 각 문자에 대한 설명입니다.

*x*  
에 지정 된 환산 변수 중 하나는 `list`합니다.

*variable-list*  
스칼라 감소가 변수의 쉼표로 구분 된 목록입니다.

*expr*  
참조 하지 않는 스칼라 형식이 포함 된 식을 *x*합니다.

*op*  
오버 로드 된 연산자를 하나만 +, &#42;,-, &amp;, ^, &#124;, &amp; &amp;, 또는 &#124; &#124;합니다.

*binop*  
오버 로드 된 연산자를 하나만 +, &#42;,-, &amp;, ^, 또는 &#124;합니다.

다음은의 예는 `reduction` 절:  
  
```cpp  
#pragma omp parallel for reduction(+: a, y) reduction(||: am)  
for (i=0; i<n; i++) {  
   a += b[i];  
   y = sum(y, c[i]);  
   am = am || b[i] == c[i];  
}  
```  
  
이 예제에 나와 있는 것 처럼 연산자 함수 호출 내부 숨겨질 수 있습니다. 사용자는 연산자에 지정 있음을 주의 해야 합니다.는 `reduction` 절 감소 작업을 일치 합니다.

하지만의 오른쪽 피연산자는 &#124; &#124; 연산자이 예제에 대 한 부작용이 없습니다는 허용 되지만 주의 해 서 사용 해야 합니다. 이 컨텍스트에서 순차 루프를 실행 하는 동안 발생할 수 없도록 보장 되는 부작용이 병렬 실행 하는 동안 발생할 수 있습니다. 이러한 차이 반복 횟수의 실행 순서는 확정적 때문에 발생할 수 있습니다.

감소에 대 한 컴파일러에 의해 사용 되는 모든 개인 변수의 초기 값을 확인 하 고 종료 연산자를 결정 하는 연산자 사용 됩니다. 연산자를 명시적으로 지정 하는 구문의 어휘 범위 밖에 감소 문을 수 있습니다. 개수에 관계 없이 `reduction` 는 지시문에 절을 지정할 수는 있지만 변수는 최대 하나에 나타날 수 있습니다 `reduction` 해당 지시문에 절.

각 변수는의 전용 복사본 *변수 목록* 만들어지면 각 스레드에 대 한 하나 처럼는 `private` 절을 사용한 것입니다. 개인 복사본이 연산자에 따라 초기화 됩니다 (아래 표 참조).

끝에 있는 지역에서 `reduction` 절이 지정 되어, 원래 개체의 각 지정 된 연산자를 사용 하 여 개인 복사본 최종 값과 원래 값을 조합한 결과 반영 하도록 업데이트 됩니다. 감소 연산자 (빼기)를 제외한 모든 연관 되며 컴파일러 계산 최종 값을 다시 연결 자유롭게 수 있습니다. (빼기 감소의 일부 결과 최종 값을 구성 하기 위해 추가 됩니다.)

첫 번째 스레드가 포함 하는 절에 도달 하 고 감소 계산이 완료 될 때까지 상태로 유지 됩니다 원래 개체의 값이 비활성화 됩니다.  일반적으로 계산 구문; 끝날 때 완료 됩니다. 그러나 경우는 `reduction` 절을 사용 하는 데 문제가 있는 구문에서 `nowait` 은 적용 원래 개체의 값 확정 때까지 유지 됩니다 모든 스레드는 완료되도록하려면장벽동기화작업이`reduction`절.

다음 표에서 사용할 수 있는 연산자 및 해당 정식 초기화 값을 나열 합니다. 실제 초기화 값은 감소 변수의 데이터 형식과 일치 됩니다.

|연산자|초기화|
|--------------|--------------------|
|+|0|
|&#42;|1|
|-|0|
|&amp;|~0|
|&#124;|0|
|^|0|
|&amp;&amp;|1|
|&#124;&#124;|0|

시의 제한 된 `reduction` 절은 다음과 같습니다.

- 형식에서 변수의 `reduction` 제외 하 고 포인터 형식과 참조 형식이 허용 되지 않습니다 절 reduction 연산자에 대해 유효 해야 합니다.

- 에 지정 된 변수는 `reduction` 절 않아야 **const**-정규화 합니다.

- 변수 또는 개인 병렬 영역 내부에 표시 되는 `reduction` 절은 **병렬** 지시문에 지정할 수 없습니다는 `reduction` 는 병렬 구문에 바인딩하는 작업 공유 지시문의 절.

   ```cpp
   #pragma omp parallel private(y)
   { /* ERROR - private variable y cannot be specified
                in a reduction clause */
      #pragma omp for reduction(+: y)
      for (i=0; i<n; i++)
         y += b[i];
   }
   
   /* ERROR - variable x cannot be specified in both
              a shared and a reduction clause */
   #pragma omp parallel for shared(x) reduction(+: x)
   ```
