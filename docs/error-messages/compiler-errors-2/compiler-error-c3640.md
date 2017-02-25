---
title: "컴파일러 오류 C3640 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3640"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3640"
ms.assetid: fcc56894-0f98-48af-8561-3bf7c7b2b93f
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 컴파일러 오류 C3640
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'member' : 지역 클래스의 가상 멤버 함수 또는 참조된 멤버 함수를 정의해야 합니다.  
  
 컴파일러에서 특정 함수를 정의해야 합니다.  
  
 다음 샘플에서는 C3640 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3640.cpp  
void f()   
{  
   struct S  
   {  
      virtual void f1();   // C3640  
      // Try the following line instead:  
      // virtual void f1(){}  
   };  
}  
```