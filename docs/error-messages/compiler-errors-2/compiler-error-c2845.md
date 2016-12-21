---
title: "컴파일러 오류 C2845 | Microsoft Docs"
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
  - "C2845"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2845"
ms.assetid: 31b28ee9-978f-403b-94d8-dbaacd24cce0
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2845
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'operator' : 이 형식에서는 포인터 산술 연산을 할 수 없습니다.  
  
 관리되는 클래스에 대한 포인터를 증가시킬 수 없습니다.  
  
 **Managed Extensions for C\+\+**  
  
 [\_\_gc](../../misc/gc.md) 클래스에 대한 포인터를 증가시킬 수 없습니다.  또한 **\/clr:oldSyntax**가 아닌 **\/clr**에서만 문자열 연산자를 사용할 수 있습니다.  
  
 다음 샘플에서는 C2845 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2845b.cpp  
// compile with: /clr:oldSyntax  
using namespace System;  
__gc class X {};  
  
int main() {  
   X *pX = new X;  
   pX++;   // C2845  
  
   String * a = new String("abc");  
   String * b = new String("def");  
   Console::WriteLine(a + b);   // C2845 not with /clr:oldSyntax  
}  
```