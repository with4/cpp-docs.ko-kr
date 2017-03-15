---
title: "A.23   Examples of the ordered Directive | Microsoft Docs"
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
ms.assetid: f8fa761b-7fc5-4447-95f9-8571e9ca31bf
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# A.23   Examples of the ordered Directive
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

순서가 지정 된 여러 개의 절을 사용할 수 있습니다 한 `for` 에 지정 된는 `ordered` 절.  첫 번째 예제에서는 API는 다음 지정 하기 때문에 정책 위반입니다.  
  
 "은 루프의 반복에는 `for` 구문을 동일한 실행 합니다 않는 `ordered` 지시문 개를 한 번에 한 두 개 이상의 실행 합니다 않는 `ordered` 지시문." \(참조 하십시오  [섹션 2.6.6](../../parallel/openmp/2-6-6-ordered-construct.md) 22 페이지\)  
  
 비규격 예제에서는 모든 반복 2 정렬 된 섹션을 실행합니다.  
  
```  
#pragma omp for ordered  
for (i=0; i<n; i++)   
{  
    ...  
    #pragma omp ordered  
    { ... }  
    ...  
    #pragma omp ordered  
    { ... }  
    ...  
}  
```  
  
 다음 규격 예제는 `for` 를 둘 이상의 구역 주문:  
  
```  
#pragma omp for ordered  
for (i=0; i<n; i++)   
{  
    ...  
    if (i <= 10)   
    {  
        ...  
        #pragma omp ordered  
        { ... }  
    }  
    ...  
    (i > 10)   
    {  
        ...  
        #pragma omp ordered  
        { ... }  
    }  
    ...  
}  
```