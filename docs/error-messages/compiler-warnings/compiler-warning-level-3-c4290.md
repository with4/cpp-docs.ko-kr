---
title: "컴파일러 경고 (수준 3) C4290 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4290"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4290"
ms.assetid: d1c6d85b-28e0-4a1f-9d48-23593337a6fb
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# 컴파일러 경고 (수준 3) C4290
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

함수가 \_\_declspec\(nothrow\)가 아님을 나타내려는 경우를 제외하고 C\+\+ 예외 사양은 무시됩니다.  
  
 Visual C\+\+에서 받아들이기는 하지만 구현하지 않는 예외 사양을 사용하여 함수를 선언했습니다.  컴파일하는 동안 무시되는 예외 사양을 사용한 코드는 다시 컴파일하고 링크하여 이 예외 사양을 지원하는 이후 버전에서 다시 사용하도록 합니다.  
  
 자세한 내용은 [예외 사양\(throw\)](../../cpp/exception-specifications-throw-cpp.md)을 참조하십시오.  
  
 다음과 같이 [warning](../../preprocessor/warning.md) pragma를 사용하여 이 경고가 발생하지 않도록 합니다.  
  
```  
#pragma warning( disable : 4290 )  
```  
  
 다음 코드 샘플에서는 C4290 경고가 발생하는 경우를 보여 줍니다.  
  
```  
// C4290.cpp  
// compile with: /EHs /W3 /c  
void f1(void) throw(int) {}   // C4290  
  
// OK  
void f2(void) throw() {}  
void f3(void) throw(...) {}  
```