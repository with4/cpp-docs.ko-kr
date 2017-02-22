---
title: "컴파일러 오류 C3800 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3800"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3800"
ms.assetid: c653240a-b6db-4437-8d65-fa58f0e6fcf4
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C3800
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'declaration': 속성과 이벤트를 혼합할 수 없습니다.  
  
 구문을 속성과 이벤트 모두로 선언할 수 없습니다.  
  
 C3800은 **\/clr:oldSyntax**를 사용하는 경우에만 발생합니다.  
  
 다음 샘플에서는 C3800 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3800.cpp  
// compile with: /clr:oldSyntax  
#using "mscorlib.dll"  
  
__delegate void MyDel();  
public __gc struct S  
{  
   __property __event void set_E(MyDel*)  
   {  
   }   // C3800  
};  
  
int main()  
{  
}  
```