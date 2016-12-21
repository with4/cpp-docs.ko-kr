---
title: "컴파일러 오류 C2523 | Microsoft Docs"
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
  - "C2523"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2523"
ms.assetid: 7951b700-8f37-45a0-beb4-a79ae0ced72e
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2523
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class::~identifier' : destructor\/finalizer 태그가 일치하지 않습니다.  
  
 소멸자 이름은 물결표\(`~`\) 다음에 클래스 이름이 와야 합니다.  생성자와 소멸자는 클래스와 이름이 동일한 멤버입니다.  
  
 다음 샘플에서는 C2523 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2523.cpp  
// compile with: /c  
class A {  
   ~B();    // C2523  
   ~A();   // OK  
};  
```