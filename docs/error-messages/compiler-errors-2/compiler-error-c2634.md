---
title: "컴파일러 오류 C2634 | Microsoft Docs"
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
  - "C2634"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2634"
ms.assetid: 58c8f2db-ac95-4a81-9355-ef3cfb0ba7b3
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2634
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'&class::member' : 참조 멤버에 대한 포인터가 잘못되었습니다.  
  
 참조 멤버에 대한 포인터가 선언되었습니다.  
  
 다음 샘플에서는 C2634 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2634.cpp  
int mem;  
struct S {  
   S() : rf(mem) { }  
   int &rf;  
};  
int (S::*pdm) = &S::rf;   // C2634  
```