---
title: "식 계산기 오류 CXX0015 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "CXX0015"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAN0015"
  - "CXX0015"
ms.assetid: 35efaf77-d578-48d8-bfc5-fdeb2a46a8b5
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 식 계산기 오류 CXX0015
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

식이 너무 복잡합니다\(스택 오버플로\).  
  
 입력한 식이 너무 복잡하거나 깊게 중첩되어 C 식 계산기가 사용할 수 있는 저장 용량을 초과했습니다.  
  
 일반적으로 오버플로는 보류 중인 계산이 너무 많은 경우에 발생합니다.  
  
 식의 각 구성 요소가 다른 부분이 계산될 때까지 기다리지 않고 즉시 계산되도록 다시 정렬하십시오.  
  
 식을 다중 명령으로 분할하십시오.  
  
 이 오류는 CAN0015와 동일합니다.