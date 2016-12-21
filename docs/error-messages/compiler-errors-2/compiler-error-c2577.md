---
title: "컴파일러 오류 C2577 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2577"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2577"
ms.assetid: fc79ef83-8362-40a2-9257-8037c3195ce4
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2577
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'member' : 소멸자\/종료자은\(는\) 반환 형식을 가질 수 없습니다.  
  
 소멸자나 종료자는 `void` 또는 다른 유형의 값을 반환할 수 없습니다.  소멸자 정의에서 `return` 문을 제거하십시오.  
  
## 예제  
 다음 샘플에서는 C2577 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2577.cpp  
// compile with: /c  
class A {  
public:  
   A() {}  
   ~A(){  
      return 0;   // C2577  
   }  
};  
```