---
title: "컴파일러 오류 C2411 | Microsoft Docs"
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
  - "C2411"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2411"
ms.assetid: 453317d3-0629-4b42-b8ea-3a0b39698ca5
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2411
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 'context'의 구조체\/공용 구조체 멤버가 잘못되었습니다.  
  
### 문제 해결을 위하여 확인해 볼 수 있는 원인  
  
1.  식별자가 이 컨텍스트에서 가시적인 구조체 또는 공용 구조체의 멤버가 아닙니다.  
  
2.  식별자가 멤버 선택\(.\) 연산자를 사용하여 지정된 구조체 또는 공용 구조체의 멤버가 아닙니다.