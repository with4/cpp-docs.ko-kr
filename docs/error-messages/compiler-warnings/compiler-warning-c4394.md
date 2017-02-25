---
title: "컴파일러 경고 C4394 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4394"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4394"
ms.assetid: 5de94de0-17e3-4e7c-92f4-5c3c1b825120
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# 컴파일러 경고 C4394
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : appdomain별 기호는 \_\_declspec\(dllexport\)로 표시할 수 없습니다.  
  
 [appdomain](../../cpp/appdomain.md) `__declspec` 한정자로 표시한 함수는 네이티브가 아닌 MSIL로 컴파일되고, 내보내기 테이블\([export](../../windows/export.md) `__declspec` 한정자\)은 관리되는 함수에 대해 지원되지 않습니다.  
  
 공용으로 액세스 가능한 관리 되는 함수를 선언할 수 있습니다.  자세한 내용은 [형식 표시](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility) 및 [멤버 표시](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Member_visibility)를 참조하십시오.  
  
 C4394는 항상 오류로서 발생합니다.  `#pragma warning` 또는 **\/wd**를 사용하여 이 경고를 해제할 수 있습니다. 자세한 내용은 [경고](../../preprocessor/warning.md) 또는 [\/w, \/Wn, \/WX, \/Wall, \/wln, \/wdn, \/wen, \/won\(경고 수준\)](../../build/reference/compiler-option-warning-level.md)을 참조하십시오.  
  
## 예제  
 다음 샘플에서는 C4394 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4394.cpp  
// compile with: /clr /c  
__declspec(dllexport) __declspec(appdomain) int g1 = 0;   // C4394  
__declspec(dllexport) int g2 = 0;   // OK  
```