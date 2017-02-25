---
title: "Compiler Error C3550 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3550"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3550"
ms.assetid: 9f2d5ffc-e429-41a1-89e3-7acc4fd47e14
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compiler Error C3550
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 컨텍스트에 일반 'decltype\(auto\)'만 사용할 수 있습니다.  
  
 `decltype(auto)`을 함수 반환 형식의 자리 표시자로 사용하는 경우 자체에서 사용되어야 합니다.  포인터 선언\(`decltype(auto*)`\), 참조 선언\(`decltype(auto&)`\) 또는 이러한 기타 모든 한정의 일부로 사용할 수 없습니다.  
  
## 참고 항목  
 [auto](../../cpp/auto-cpp.md)