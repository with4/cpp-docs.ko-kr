---
title: "컴파일러 오류 C2692 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2692"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2692"
ms.assetid: 02ade3b4-b757-448b-b065-d7d71bc3f441
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# 컴파일러 오류 C2692
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function\_name' : C 컴파일러에는 '\/clr' 옵션으로 완전히 프로토타입화된 함수가 있어야 합니다.  
  
 .NET 관리 코드에 대해 컴파일할 경우 C 컴파일러에는 ANSI 함수 선언이 있어야 합니다.  또한 함수가 매개 변수를 사용하지 않는 경우에는 `void`를 매개 변수 형식으로 명시적으로 선언해야 합니다.