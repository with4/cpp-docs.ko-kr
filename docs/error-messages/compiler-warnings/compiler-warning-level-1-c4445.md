---
title: "컴파일러 경고 (수준 1) C4445 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4445"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4445"
ms.assetid: 535e92a0-ba08-4dfc-89b2-af2dcdd7caeb
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 경고 (수준 1) C4445
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function': WinRT 또는 관리되는 형식에서 가상 메서드는 private일 수 없습니다.  
  
 가상 함수가 private인 경우 파생된 형식에서 액세스할 수 없습니다.  이 오류를 해결하려면 가상 멤버 함수의 접근성을 보호됨이나 공용으로 변경합니다.