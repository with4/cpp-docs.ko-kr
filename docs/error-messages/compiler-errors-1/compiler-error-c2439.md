---
title: "컴파일러 오류 C2439 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2439"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2439"
ms.assetid: 3c5dbe5c-b7d3-4bb0-8619-92f6e280461e
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 컴파일러 오류 C2439
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 멤버를 초기화할 수 없습니다.  
  
 클래스, 구조체 또는 공용 구조체 멤버를 초기화할 수 없습니다.  
  
### 문제 해결을 위하여 확인해 볼 수 있는 원인  
  
1.  간접 참조 기본 클래스 또는 구조체를 초기화하려고 했습니다.  
  
2.  클래스 또는 구조체의 상속된 멤버를 초기화하려고 했습니다.  상속된 멤버는 클래스 또는 구조체의 생성자에 의해 초기화해야 합니다.