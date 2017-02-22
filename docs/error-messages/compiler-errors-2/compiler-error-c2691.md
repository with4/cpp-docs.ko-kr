---
title: "컴파일러 오류 C2691 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2691"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2691"
ms.assetid: 6925f8f3-ea60-4909-91e6-b781492c645d
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# 컴파일러 오류 C2691
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'data type' : 관리되는 배열 또는 WinRT 배열은 이 요소 형식을 사용할 수 없습니다.  
  
 관리되는 배열 또는 WinRT 배열의 요소 형식은 값 형식이나 참조 형식일 수 있습니다.  
  
 다음 샘플에서는 C2691 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2691a.cpp  
// compile with: /clr  
class A {};  
  
int main() {  
   array<A>^ a1 = gcnew array<A>(20);   // C2691  
   array<int>^ a2 = gcnew array<int>(20);   // value type OK  
}  
```  
  
 다음 샘플에서는 C2691 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2691b.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
int main() {  
   int * a1 __gc[];   // C2691  
   int * a1 = new int [20];   // OK  
}  
```  
  
 C2691은 Managed Extensions for C\+\+를 사용하여 가변 배열을 정의하는 경우에 발생할 수도 있습니다.  가변 배열은 현재 구문에서 지원됩니다. 자세한 내용은 [Arrays](../../windows/arrays-cpp-component-extensions.md)을 참조하세요.  
  
 다음 샘플에서는 C2691 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2691c.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
using namespace System;  
int main() {  
   Int32 myJaggedArray[][] = new Int32 [50][];   // C2691  
}  
```