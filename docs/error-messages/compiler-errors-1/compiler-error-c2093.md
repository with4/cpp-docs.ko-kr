---
title: "컴파일러 오류 C2093 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2093"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2093"
ms.assetid: 17529a70-9169-46b5-9fc6-57a5ce224e6a
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 오류 C2093
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'variable1' : 자동 변수 'variable2'의 주소를 사용하여 초기화할 수 없습니다.  
  
 [\/Za](../../build/reference/za-ze-disable-language-extensions.md)를 사용하여 컴파일하면 프로그램은 자동 변수의 주소를 이니셜라이저로 사용하려고 합니다.  
  
 다음 샘플에서는 C2093 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2093.c  
// compile with: /Za /c  
void func() {  
   int li;   // an implicit auto variable  
   int * s[]= { &li };   // C2093 address is not a constant  
  
   // OK  
   static int li2;  
   int * s2[]= { &li2 };  
}  
```