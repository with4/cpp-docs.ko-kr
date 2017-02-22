---
title: "single | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Single"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "single OpenMP directive"
ms.assetid: 85cf94fb-cb9c-4d82-8609-adffa9f552e1
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# single
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

코드 섹션을 마스터 스레드가 아닌 단일 스레드에서 실행 되도록 지정할 수 있습니다.  
  
## 구문  
  
```  
#pragma omp single [clauses]   
{  
   code_block   
}  
```  
  
#### 매개 변수  
 `clause`\(선택적 요소\)  
 0 개 이상의 절입니다.  목록에 대 한 설명 부분에서 지원 절을 참조 하십시오.  **단일**.  
  
## 설명  
 해당  **단일** 지시문 다음 OpenMP 절을 지원 합니다.  
  
-   [copyprivate](../../../parallel/openmp/reference/copyprivate.md)  
  
-   [firstprivate](../../../parallel/openmp/reference/firstprivate.md)  
  
-   [nowait](../../../parallel/openmp/reference/nowait.md)  
  
-   [private](../../../parallel/openmp/reference/private-openmp.md)  
  
 [master](../../../parallel/openmp/reference/master.md) 지시문을 사용 하면 코드 부분 마스터 스레드에서만 실행 되도록 지정 합니다.  
  
 자세한 내용은 [2.4.3 single Construct](../../../parallel/openmp/2-4-3-single-construct.md)를 참조하십시오.  
  
## 예제  
  
```  
// omp_single.cpp  
// compile with: /openmp   
#include <stdio.h>  
#include <omp.h>  
  
int main() {  
   #pragma omp parallel num_threads(2)  
   {  
      #pragma omp single  
      // Only a single thread can read the input.  
      printf_s("read input\n");  
  
      // Multiple threads in the team compute the results.  
      printf_s("compute results\n");  
  
      #pragma omp single  
      // Only a single thread can write the output.  
      printf_s("write output\n");  
    }  
}  
```  
  
  **입력을 읽기**  
**결과 계산 합니다.**  
**결과 계산 합니다.**  
**출력 작성**   
## 참고 항목  
 [Directives](../../../parallel/openmp/reference/openmp-directives.md)