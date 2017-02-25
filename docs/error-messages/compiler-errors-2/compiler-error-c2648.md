---
title: "컴파일러 오류 C2648 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2648"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2648"
ms.assetid: ce338337-9154-4f85-bb61-b05fdbfad75d
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C2648
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 멤버를 기본 매개 변수로 사용하려면 정적 멤버이어야 합니다.  
  
 비정적 멤버가 기본 매개 변수로 사용되었습니다.  
  
 다음 샘플에서는 C2648 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2648.cpp  
// compile with: /c  
class C {  
public:  
   int i;  
   static int j;  
   void func1( int i = i );  // C2648  i is not static  
   void func2( int i = j );  // OK  
};  
```