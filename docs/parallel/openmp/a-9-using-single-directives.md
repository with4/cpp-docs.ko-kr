---
title: "A.9   Using single Directives | Microsoft Docs"
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
ms.assetid: 0c0f9495-5794-4db9-883b-a12e3a9f1328
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# A.9   Using single Directives
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

다음 예제는 `single` 지시문 \([2.4.3 절](../../parallel/openmp/2-4-3-single-construct.md) 15 페이지\).  예제에서 스레드가 하나만 \(발견 한 첫 번째 스레드가 보통은 `single` 지시문\) 진행 메시지를 출력 합니다.  하는 스레드가 실행할 때 사용자가 어떠한가 정도 해서는 안됩니다는 `single` 섹션입니다.  다른 모든 스레드를 건너뛸 수는 `single` 섹션 및 장애물의 끝에서 중지는 `single` 생성 합니다.  스레드가 실행을 기다리는 다른 스레드가 처리 하는 경우는 `single` 섹션에서는 `nowait` 절에서 지정 된 수의 `single` 지시문.  
  
```  
#pragma omp parallel  
{  
    #pragma omp single  
        printf_s("Beginning work1.\n");  
    work1();  
    #pragma omp single  
        printf_s("Finishing work1.\n");  
    #pragma omp single nowait  
        printf_s("Finished work1 and beginning work2.\n");  
    work2();  
}  
```