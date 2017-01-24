---
title: "컴파일러 경고 (수준 1) C4297 | Microsoft Docs"
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
  - "C4297"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4297"
ms.assetid: ba92fcdc-9f70-4f60-abe6-281f9582ca59
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 1) C4297
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function': 함수는 예외를 throw하지 않도록 지정되었으나 예외를 throw했습니다.  
  
 함수 선언에는 \(암시적일 수 있는\) `noexcept` 지정자, 빈 `throw` 예외 지정자 또는 [\_\_declspec\(nothrow\)](../../cpp/nothrow-cpp.md) 특성이 포함되고, 정의에는 하나 이상의 [throw](../../cpp/try-throw-and-catch-statements-cpp.md) 문이 포함됩니다.  C4297를 해결하려면 선언된 `__declspec(nothrow)`, `noexcept(true)` 또는 `throw()`인 함수에서 예외를 throw하도록 시도하지 마세요.  또는 `noexcept`, `throw()` 또는 `__declspec(nothrow)` 사양을 제거합니다.  
  
 기본적으로 컴파일러에서는 사용자 정의 소멸자 및 비할당자 함수와 컴파일러에서 생성된 특수 멤버 함수에 대한 암시적 `noexcept(true)` 지정자를 생성합니다.  이는 ISO C\+\+11 표준을 따릅니다.  암시적 noexcept 지정자의 생성을 방지하고 컴파일러를 Visual Studio 2013의 비표준 동작으로 되돌리려면 **\/Zc:implicitNoexcept\-** 컴파일러 옵션을 사용합니다.  자세한 내용은 [\/Zc:implicitNoexcept\(암시적 예외 지정자\)](../../build/reference/zc-implicitnoexcept-implicit-exception-specifiers.md)를 참조하세요.  
  
 예외 사양에 대한 자세한 내용은 [예외 사양\(throw\)](../../cpp/exception-specifications-throw-cpp.md)을 참조하세요.  또한 컴파일 시간에 예외 처리 동작을 수정하는 방법에 대한 자세한 내용은 [\/EH\(예외 처리 모델\)](../../build/reference/eh-exception-handling-model.md)를 참조하세요.  
  
 이 경고는 C\+\+ 함수여도 extern "C"로 표시된 \_\_declspec\([dllexport](../../cpp/dllexport-dllimport.md)\) 함수에 대해서도 생성됩니다.  
  
 다음 샘플에서는 C4297 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4297.cpp  
// compile with: /W1 /LD  
void __declspec(nothrow) f1()   // declared nothrow  
// try the following line instead  
// void f1()  
{  
   throw 1;   // C4297  
}  
```