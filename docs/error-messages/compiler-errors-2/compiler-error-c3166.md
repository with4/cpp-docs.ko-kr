---
title: "컴파일러 오류 C3166 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3166"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3166"
ms.assetid: ec3e330d-c15d-4158-8268-09101486c566
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# 컴파일러 오류 C3166
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'pointer' : 내부 \_\_gc 포인터의 포인터를 'type'의 멤버로 선언할 수 없습니다.  
  
 컴파일러가 잘못된 포인터 선언\([\_\_gc](../../misc/gc.md) 포인터에 대해 [\_\_nogc](../../misc/nogc.md) 포인터 선언\)을 발견했습니다.  이 구문은 이후 릴리스에서 지원될 것입니다.  
  
 C3166은 **\/clr:oldSyntax**를 사용하는 경우에만 발생합니다.  
  
 다음 샘플에서는 C3166 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3166.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
using namespace System;  
  
__gc struct G {  
   int __gc* __nogc* p;   // C3166  
};  
  
public __gc class H {  
public:  
   Int32 __gc* __nogc* p;   // C3166  
};  
  
public __value struct I {  
   int __gc* __nogc* p;   // C3166  
};  
  
public __value class J {  
public:  
   int __gc* __nogc* p;   // C3166  
};  
  
int main() {  
   G* pG = new G;  
   H* pH = new H;  
}  
```