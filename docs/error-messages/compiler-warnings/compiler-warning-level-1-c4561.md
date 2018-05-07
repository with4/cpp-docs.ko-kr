---
title: 컴파일러 경고 (수준 1) C4561 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4561
dev_langs:
- C++
helpviewer_keywords:
- C4561
ms.assetid: 3a10c12c-601b-4b6c-9861-331fd022e021
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d4862d7f570faea3e362a505e67bddaf504b32de
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4561"></a>컴파일러 경고(수준 1) C4561
'와 호환 되지 않는 ' __fastcall는 ' / clr' 옵션: 변환할 '\__stdcall'  
  
 [__fastcall](../../cpp/fastcall.md) 함께 함수 호출 규칙을 사용할 수 없습니다는 [/clr](../../build/reference/clr-common-language-runtime-compilation.md) 컴파일러 옵션입니다. 컴파일러에 대 한 호출을 무시 `__fastcall`합니다. 에 대 한 호출을 제거 하거나이 경고를 해결 하려면 **__fastcall** 또는 없이 컴파일 **/clr**합니다.  
  
 다음 샘플에서는 C4561 오류가 생성 됩니다.  
  
```  
// C4561.cpp  
// compile with: /clr /W1 /c  
// processor: x86  
void __fastcall Func(void *p);   // C4561, remove __fastcall to resolve  
```