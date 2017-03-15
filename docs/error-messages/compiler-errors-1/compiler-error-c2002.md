---
title: "컴파일러 오류 C2002 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2002"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2002"
ms.assetid: 91982314-203a-4de1-b884-94e39a623f61
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# 컴파일러 오류 C2002
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

와이드 문자 상수가 잘못되었습니다.  
  
 멀티바이트 문자 상수가 잘못되었습니다.  
  
### 문제 해결을 위하여 확인해 볼 수 있는 원인  
  
1.  와이드 문자 상수에 예상보다 많은 바이트가 포함되어 있습니다.  
  
2.  표준 헤더인 STDDEF.h가 포함되어 있지 않습니다.  
  
3.  와이드 문자를 보통 문자열 리터럴과 연결할 수 없습니다.  
  
4.  와이드 문자 상수는 반드시 'L' 문자로 시작해야 합니다.  
  
    ```  
    L'mbconst'  
    ```  
  
5.  Microsoft C\+\+의 경우 전처리기 지시문의 텍스트 인수는 ASCII여야 합니다.  예를 들어 `#pragma message(L"string")` 지시문은 올바르지 않습니다.