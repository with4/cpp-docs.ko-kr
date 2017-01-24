---
title: "A.6   Using the lastprivate Clause | Microsoft Docs"
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
ms.assetid: cf3bf0cc-aa46-4e44-9433-e2969e3be2c1
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# A.6   Using the lastprivate Clause
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

올바른 실행 때로는 마지막 반복 하는 루프를 변수에 지정 하는 값에 따라 다릅니다.  이러한 프로그램 같은 모든 인수에 변수를 나열 해야 합니다는 `lastprivate` 절 \([섹션 2.7.2.3](../../parallel/openmp/2-7-2-3-lastprivate.md) 페이지 27\) 변수 값 루프가 순차적으로 실행 될 때와 동일 하.  
  
```  
#pragma omp parallel  
{  
   #pragma omp for lastprivate(i)  
      for (i=0; i<n-1; i++)  
         a[i] = b[i] + b[i+1];  
}  
a[i]=b[i];  
```  
  
 앞의 예제에서 값을 `i` 병렬 영역 끝에 용량이 됩니다 `n–1`, 순차적인 경우 처럼.