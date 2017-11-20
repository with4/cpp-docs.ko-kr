---
title: "컴파일러 경고 C4439 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4439
dev_langs: C++
helpviewer_keywords: C4439
ms.assetid: 9449958f-f407-4824-829b-9e092f2af97d
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: eec228922a6f5796587243fe2d1f2c6cc1cf6b1c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-c4439"></a>컴파일러 경고 C4439
'function': 서명에 관리 되는 형식과 함수 정의는 __clrcall 호출 규칙이 있어야 합니다.  
  
 컴파일러는 암시적으로 호출 규칙을 대체 [__clrcall](../../cpp/clrcall.md)합니다. 이 경고를 해결 하려면 제거의 `__cdecl` 또는 `__stdcall` 호출 규칙입니다.  
  
 C4439은 항상 오류로 실행 됩니다. 와 함께이 경고를 해제할 수 있습니다는 `#pragma warning` 또는 **/wd**; 참조 [경고](../../preprocessor/warning.md) 또는 [/w, /W0, /W1, /W2, /W3, /W4, /w1, /w2, /w3, /w4, /Wall, /wd, / we, /wo /Wv, /WX (경고 수준)](../../build/reference/compiler-option-warning-level.md)자세한 정보에 대 한 합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 c4439 경고가 발생 합니다.  
  
```  
// C4439.cpp  
// compile with: /clr  
void __stdcall f( System::String^ arg ) {}   // C4439  
void __clrcall f2( System::String^ arg ) {}   // OK  
void f3( System::String^ arg ) {}   // OK  
```