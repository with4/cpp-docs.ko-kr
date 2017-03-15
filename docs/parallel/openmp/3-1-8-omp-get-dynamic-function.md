---
title: "3.1.8 omp_get_dynamic Function | Microsoft Docs"
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
ms.assetid: c03e2daf-29c9-49e3-9b67-b980ad1ab195
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 3.1.8 omp_get_dynamic Function
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**Omp\_get\_dynamic** 함수가 동적 조정 스레드를 사용 하 고 그렇지 않으면 0을 반환 하는 경우 0이 아닌 값을 반환 합니다.  형식은 다음과 같습니다.  
  
```  
#include <omp.h>  
int omp_get_dynamic(void);  
```  
  
 구현을 동적 조정 스레드를 구현 하지 않는 경우이 함수는 항상 0을 반환 합니다.  
  
## 상호 참조:  
  
-   동적 스레드 조정에 대 한 설명은 참조 하십시오.  [섹션 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) 39 페이지에 있습니다.