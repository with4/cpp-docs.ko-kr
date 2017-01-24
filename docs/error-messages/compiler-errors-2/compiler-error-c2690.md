---
title: "컴파일러 오류 C2690 | Microsoft Docs"
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
  - "C2690"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2690"
ms.assetid: f165a806-14bd-4942-99b7-8a9fc7dea227
caps.latest.revision: 16
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2690
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'operator': WinRT 또는 관리되는 배열에서 포인터 산술 연산을 수행할 수 없습니다.  
  
 포인터 산술 연산은 WinRT 또는 관리되는 배열에서 허용되지 않습니다.  배열 인덱스 표기법을 사용하여 배열을 트래버스합니다.  
  
 **Managed Extensions for C\+\+**  
  
 포인터 산술 연산은 [\_\_gc](../../misc/gc.md) 배열에서 허용되지 않습니다.  배열 인덱스 표기법을 사용하여 배열을 트래버스합니다.  
  
 다음 샘플에서는 C2690 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2690b.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
using namespace System;  
  
int main() {  
   String* x[] = new String*[10];  
   x[0] = "test";  
   Console::WriteLine(x[0]);  
   x++;   // C2690  
}  
```