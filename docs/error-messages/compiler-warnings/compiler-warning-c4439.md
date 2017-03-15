---
title: "컴파일러 경고 C4439 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4439"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4439"
ms.assetid: 9449958f-f407-4824-829b-9e092f2af97d
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 컴파일러 경고 C4439
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : 시그니처에 관리되는 형식이 있는 함수 정의에는 \_\_clrcall 호출 규칙이 있어야 합니다.  
  
 컴파일러에서 암시적으로 호출 규칙을 [\_\_clrcall](../../cpp/clrcall.md)로 대체했습니다.  이 경고를 해결하려면 `__cdecl` 또는 `__stdcall` 호출 규칙을 제거하십시오.  
  
 C4439는 항상 오류로서 발생합니다.  `#pragma warning` 또는 **\/wd**를 사용하여 이 경고를 해제할 수 있습니다. 자세한 내용은 [경고](../../preprocessor/warning.md) 또는 [\/w, \/Wn, \/WX, \/Wall, \/wln, \/wdn, \/wen, \/won\(경고 수준\)](../../build/reference/compiler-option-warning-level.md)을 참조하십시오.  
  
## 예제  
 다음 샘플에서는 C4439 경고가 발생하는 경우를 보여 줍니다.  
  
```  
// C4439.cpp  
// compile with: /clr  
void __stdcall f( System::String^ arg ) {}   // C4439  
void __clrcall f2( System::String^ arg ) {}   // OK  
void f3( System::String^ arg ) {}   // OK  
```