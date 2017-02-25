---
title: "컴파일러 오류 C3842 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3842"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3842"
ms.assetid: 41a1a44a-c618-40a2-8d26-7da27d14095d
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# 컴파일러 오류 C3842
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function': WinRT 또는 관리되는 형식의 멤버 함수에 'const' 및 'volatile' 한정자를 사용할 수 없습니다.  
  
 [const](../../cpp/const-cpp.md) 및 [volatile](../../cpp/volatile-cpp.md)은 Windows 런타임 또는 관리되는 형식의 멤버 함수에서 지원되지 않습니다.  
  
 다음 샘플에서는 C3842를 생성합니다.  
  
```  
// C3842a.cpp  
// compile with: /clr /c  
public ref struct A {  
   void f() const {}   // C3842  
   void f() volatile {}   // C3842  
  
   void f() {}  
};  
  
```