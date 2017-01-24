---
title: "컴파일러 오류 C3808 | Microsoft Docs"
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
  - "C3808"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3808"
ms.assetid: 2ee8ac97-3ea4-417a-8710-be73a7f98cf4
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3808
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : ComImport 특성이 있는 클래스는 'member' 멤버를 정의할 수 없습니다. abstract 또는 dllimport 함수만 허용됩니다.  
  
 <xref:System.Runtime.InteropServices.ComImportAttribute>에서 파생된 형식은 `member`를 정의할 수 없습니다.  
  
## 예제  
 다음 샘플에서는 C3808 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3808.cpp  
// compile with: /c /clr:pure user32.lib  
using namespace System::Runtime::InteropServices;  
  
[System::Runtime::InteropServices::ComImportAttribute()]  
ref struct S1 {  
   int f() {}   // C3808  
   virtual int g() abstract;   // OK  
  
   [DllImport("msvcrt.dll")]  
   int printf(System::String ^, int i);   // OK  
};  
```