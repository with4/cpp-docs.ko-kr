---
title: "클래스 범위가 있는 이름의 링크 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "클래스 이름[C++], 링크"
  - "클래스 범위[C++], 이름의 링크"
  - "클래스[C++], 이름"
  - "클래스[C++], 범위"
  - "외부 링크, 범위 링크 규칙"
  - "링크[C++], 범위 링크 규칙"
  - "이름[C++], 범위 링크 규칙"
  - "범위[C++], 클래스 이름"
  - "범위[C++], 링크 규칙"
ms.assetid: 45275ff3-6e94-4967-82c8-ba540ef4da28
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# 클래스 범위가 있는 이름의 링크
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

다음 링크 규칙은 클래스 범위가 있는 이름에 적용됩니다.  
  
-   정적 클래스 멤버에는 외부 링크가 있습니다.  
  
-   클래스 멤버 함수에는 외부 링크가 있습니다.  
  
-   열거자 및 `typedef` 이름에는 링크가 없습니다.  
  
 **Microsoft 전용**  
  
-   `friend` 함수로 선언된 함수에는 외부 링크가 있어야 합니다.  정적 함수를 `friend`로 선언하면 오류가 발생합니다.  
  
 **Microsoft 전용 종료**  
  
## 참고 항목  
 [프로그램 및 링크](../cpp/program-and-linkage-cpp.md)