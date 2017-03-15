---
title: "컴파일러 오류 C2557 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2557"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2557"
ms.assetid: 48a33d82-aa16-4658-b346-2311fcb39864
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 컴파일러 오류 C2557
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier': 전용 및 보호된 멤버는 생성자 없이 초기화할 수 없습니다.  
  
 멤버와 friend만 private 또는 protected 멤버에 값을 할당할 수 있습니다. public이 아닌 멤버는 클래스 생성자에서 초기화해야 합니다.