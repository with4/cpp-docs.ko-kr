---
title: "컴파일러 경고 (수준 1) C4124 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4124"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4124"
ms.assetid: c08c3a65-9584-47a1-a147-44f00c4b230e
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 컴파일러 경고 (수준 1) C4124
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\_\_fastcall과 함께 스택 검사를 수행하는 것은 비효율적입니다.  
  
 스택 검사가 설정된 상태에서 `__fastcall` 키워드가 사용되었습니다.  
  
 `__fastcall` 규칙은 빠른 코드를 생성하지만 스택 검사는 느린 코드를 생성합니다.  `__fastcall`을 사용할 경우에는 **check\_stack** pragma 또는 \/Gs로 스택 검사를 해제시키십시오.  
  
 이 경고는 이러한 조건으로 선언된 첫째 함수에 대해서만 발생됩니다.