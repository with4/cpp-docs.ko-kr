---
title: "omp_set_nested | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "omp_set_nested"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "omp_set_nested OpenMP function"
ms.assetid: fa1cb08c-7b8b-42c9-8654-2c33dcffb5b6
caps.latest.revision: 13
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# omp_set_nested
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

중첩 된 병렬 처리 가능 합니다.  
  
## 구문  
  
```  
void omp_set_nested(  
   int val  
);  
```  
  
## 설명  
 다음은 각 매개 변수에 대한 설명입니다.  
  
 `val`  
 0이 아닌 경우 중첩 된 병렬 처리 수 있습니다.  0 이면 중첩 된 병렬 처리를 사용할 수 없습니다.  
  
## 설명  
 중첩 OMP 병렬 처리 수 있습니다이 설정 되어 있는 `omp_set_nested`, 또는 설정의 [OMP\_NESTED](../../../parallel/openmp/reference/omp-nested.md) 환경 변수.  
  
 설정에 대 한 `omp_set_nested` 의 설정 보다 우선 합니다는 `OMP_NESTED` 환경 변수입니다.  
  
 병렬 영역을 중첩 시키는 경우 스레드 수를 엄청나게 증가 하기 때문에 사용 하는 경우 환경 변수 그렇지 않으면 작동 하는 프로그램을 중단할 수 있습니다.  예를 들어 일반적 OMP 스레드 4에 설정할 6 회와를 재귀적으로 검색 \(4 6의\) 4, 096을 필요로 하는 함수를 스레드, 스레드 수가 프로세서 수를 초과 하는 경우 응용 프로그램의 성능이 저하 됩니다.  한 가지 예외는 응용 프로그램이 I\/O 바인딩 될 것입니다.  
  
 사용 [omp\_get\_nested](../../../parallel/openmp/reference/omp-get-nested.md) 의 현재 설정을 표시 하려면 `omp_set_nested`.  
  
 자세한 내용은 [3.1.9 omp\_set\_nested Function](../../../parallel/openmp/3-1-9-omp-set-nested-function.md)를 참조하십시오.  
  
## 예제  
  
```  
// omp_set_nested.cpp  
// compile with: /openmp  
#include <stdio.h>  
#include <omp.h>  
  
int main( )   
{  
    omp_set_nested(1);  
    omp_set_num_threads(4);  
    printf_s("%d\n", omp_get_nested( ));  
    #pragma omp parallel  
        #pragma omp master  
        {  
            printf_s("%d\n", omp_get_nested( ));  
        }  
}  
```  
  
  **1**  
**1**   
## 참고 항목  
 [Functions](../../../parallel/openmp/reference/openmp-functions.md)