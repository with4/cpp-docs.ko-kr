---
title: "2.7.2.6 reduction | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: e7630a15-2978-4dbe-a29b-3a46371a0151
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 2.7.2.6 reduction
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

나타나는 스칼라 변수에서이 절을 감소 수행  *변수 목록*, 운영자 op 사용 합니다.  구문에는 `reduction` 절은 다음과 같습니다:  
  
```  
  
reduction(  
op  
:  
variable-list  
)  
  
```  
  
 일반적으로 감소 문으로 다음 형식 중 하나를 지정 합니다.  
  
```  
  
        x     =  x     op     expr  
x     binop=  expr  
x     =  expr     op     x            (except for subtraction)  
x++  
++x  
x--  
--x  
```  
  
 다음은 각 문자에 대한 설명입니다.  
  
 *x*  
 지정 된 감소 변수 중 하나는 `list`.  
  
 *변수 목록*  
 감소 스칼라 변수 목록을 쉼표로 구분 합니다.  
  
 *expr 인수*  
 식을 사용 하 여 참조 되지 않은 스칼라 형식  *x*.  
  
 `op`  
 오버 로드 된 연산자 중 하나를 제외한 \+, \*,\-, &, ^, &#124;, & &, 또는 &#124; &#124;.  
  
 `binop`  
 오버 로드 된 연산자 중 하나를 제외한 \+, \*,\-, &, ^, 나.  
  
 다음은 예입니다 있는 `reduction` 절.  
  
```  
#pragma omp parallel for reduction(+: a, y) reduction(||: am)  
for (i=0; i<n; i++) {  
   a += b[i];  
   y = sum(y, c[i]);  
   am = am || b[i] == c[i];  
}  
```  
  
 예제에서와 같이 연산자 함수 호출 내부를 숨길 수 있습니다.  사용자가 연산자에 지정 된 주의 해야 있는 `reduction` 절과 일치 하는 축소 작업.  
  
 하지만의 오른쪽 피연산자는 &#124; &#124; 연산자이 예제에서는 의도 된, 사용할 수 있지만 주의 해 서 사용 해야 합니다.  이 컨텍스트에서 순차 루프를 실행 하는 동안 발생 하지 해야 부작용 병렬 실행 하는 동안 발생할 수 있습니다.  반복의 실행 순서를 결정 되지 않은 때문에 이러한 차이가 발생할 수 있습니다.  
  
 운영자 감소에 대해 컴파일러에서 사용 되는 모든 개인 변수의 초기 값을 확인 하 고 종료 연산자를 확인에 사용 됩니다.  연산자를 명시적으로 지정 구문 어휘 범위 밖으로 감소 문이 있습니다.  원하는 수의 `reduction` 절을 지시문에서 지정할 수 있지만 변수를 최대 하나만 표시 될 수 있습니다 `reduction` 지시문에 대 한 절.  
  
 개인 복사본에서 각 변수  *변수 목록* , 각 스레드에 대 한 만들어집니다 처럼는 `private` 절을 사용 했습니다.  개인 복사 연산자에 따라 초기화 됩니다 \(다음 표 참조\).  
  
 해당 지역에 있는 끝에는 `reduction` 절 지정 되었습니다, 원래 개체의 원래 값과 최종 값을 각각 지정 된 연산자를 사용 하 여 개인 복사본에 결합 한 결과 반영 하도록 업데이트 됩니다.  감소 연산자 \(빼기\)를 제외 하 고 모두 연관 되 고 컴파일러 자유롭게 최종 값의 다시 연결 될 수 있습니다.  \(일부 결과의 빼기 감소는 최종 값에 추가 됩니다.\)  
  
 첫 번째 스레드가 포함 된 절에 도달 하 고 감소 계산이 완료 될 때까지 그렇게 남아 경우 원래 개체의 값을 비활성화 상태가 됩니다.  일반적으로 계산 된 구조 끝에 완료 됩니다. 그러나 경우는 `reduction` 절을 사용 하는 구문에 `nowait` 입니다 장애물 동기화 스레드를 모두 완료 했는지 확인 하려면 완료할 때까지 적용, 원래 개체의 값을 결정할 수 없는 남아 있는 `reduction` 절.  
  
 다음 표에서 사용할 수 있는 연산자 및 정식 초기화 값을 나열 합니다.  실제 초기화 값 감소 변수 데이터 형식으로 일관 되 게 됩니다.  
  
|Operator|초기화|  
|--------------|---------|  
|\+|0|  
|\*|1|  
|\-|0|  
|&|~0|  
|&#124;|0|  
|^|0|  
|&&|1|  
|&#124;&#124;|0|  
  
 제한에는 `reduction` 절은 다음과 같습니다:  
  
-   형식에 있는 변수는 `reduction` 절 여야 감소 연산자에 대 한 유효한 포인터 형식 및 참조 형식에는 허용 되지 것을 제외 하 고.  
  
-   지정 된 변수를 `reduction` 절 이어야  **const**\-한정 된.  
  
-   변수는 병렬 영역 내부에서는 개인 또는 표시에 `reduction` 절에  **병렬** 지시문에 지정 될 수 없습니다는 `reduction` 병렬 구문에 바인딩되는 작업 공유 지시문의 절.  
  
    ```  
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