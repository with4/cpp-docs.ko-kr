---
title: "심각한 오류 C1054 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1054"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1054"
ms.assetid: 9cfb7307-b22a-4418-b7c0-2621b0ab5b1b
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 심각한 오류 C1054
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

컴파일러 한계 : 이니셜라이저가 너무 많이 중첩되었습니다.  
  
 코드가 이니셜라이저의 중첩 한계\(초기화되는 형식의 조합에 따라 10\-15 수준\)를 초과합니다.  
  
### 문제를 해결하려면 다음과 같은 해결책을 사용해 보십시오.  
  
1.  초기화 중인 데이터 형식을 간단하게 만들어서 중첩 수준을 줄입니다.  
  
2.  선언한 후에 변수를 별도의 문에서 초기화합니다.