---
title: "3.3.2 omp_get_wtick Function | Microsoft Docs"
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
ms.assetid: 1ad08500-bcb0-40d9-a81f-f131819006c9
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 3.3.2 omp_get_wtick Function
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`omp_get_wtick` 함수 반환 배정밀도 부동 소수점 값 초로 연속 클록 틱 수 사이입니다.  형식은 다음과 같습니다.  
  
```  
#include <omp.h>  
double omp_get_wtick(void);  
```