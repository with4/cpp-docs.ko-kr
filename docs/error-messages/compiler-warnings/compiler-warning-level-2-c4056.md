---
title: "컴파일러 경고 (수준 2) C4056 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4056"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4056"
ms.assetid: a3c3a9b8-ec30-452d-96cb-3694adcce789
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 2) C4056
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

부동 소수점 상수 산술 연산에서 오버플로가 발생했습니다.  
  
 부동 소수점 상수 산술 연산은 최대 허용 값을 초과하는 결과를 생성합니다.  
  
 이 경고는 상수 산술 연산 중에 수행되는 컴파일러 최적화로 인해 발생할 수 있습니다.  최적화\([\/Od](../../build/reference/od-disable-debug.md)\)를 해제할 때 이 경고가 나타나지 않으면 이 경고를 무시해도 됩니다.  
  
 다음 샘플에서는 C4056 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4056.cpp  
// compile with: /W2 /LD  
#pragma warning (default : 4056)  
float fp_val = 1.0e300 * 1.0e300;   // C4056  
```