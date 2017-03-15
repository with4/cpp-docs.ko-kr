---
title: "컴파일러 오류 C2534 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2534"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2534"
ms.assetid: 481f9f54-5b51-4aa0-8eea-218f10807705
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 오류 C2534
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 생성자는 값을 반환할 수 없습니다.  
  
 생성자는 값을 반환할 수 없으며 `void` 반환 형식이 아니더라도 반환 형식을 사용할 수 없습니다.  
  
 이 오류는 생성자 정의에서 `return` 문을 제거하여 해결할 수 있습니다.  
  
 다음 샘플에서는 C2534 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2534.cpp  
class A {  
public:  
   int i;  
   A() { return i; }   // C2534  
};  
```