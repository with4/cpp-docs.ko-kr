---
title: "3.1.10 omp_get_nested Function | Microsoft Docs"
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
ms.assetid: 48736a25-5c6e-4e2d-aad0-421087663a3c
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 3.1.10 omp_get_nested Function
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`omp_get_nested` 함수 반환 중첩 된 병렬 처리를 사용 하는 경우 0이 아닌 값이 고 0 사용 하지 않는 경우.  중첩 된 병렬 처리에 대 한 자세한 내용은 섹션 3.1.9 40 페이지에서 참조 하십시오.  형식은 다음과 같습니다.  
  
```  
#include <omp.h>  
int omp_get_nested(void);  
```  
  
 중첩 된 병렬 처리 구현 구현 하지 않는 경우이 함수는 항상 0을 반환 합니다.