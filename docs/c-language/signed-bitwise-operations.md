---
title: "부호 있는 비트 연산 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "비트 연산"
  - "부호 있는 비트 연산"
ms.assetid: 1e5cf65b-ee32-41a0-a5c2-82c1854091f6
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 부호 있는 비트 연산
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**ANSI 3.3** 부호 있는 정수에 대한 비트 연산의 결과  
  
 부호 있는 정수에 대한 비트 연산은 부호 없는 정수에 대한 비트 연산과 동일하게 작동합니다.  예를 들어, `–16 & 99`는 이진 형식으로 다음과 같이 표현될 수 있습니다.  
  
```  
  11111111 11110000  
& 00000000 01100011  
  _________________  
  00000000 01100000  
```  
  
 비트 AND의 결과는 96입니다.  
  
## 참고 항목  
 [정수](../c-language/integers.md)