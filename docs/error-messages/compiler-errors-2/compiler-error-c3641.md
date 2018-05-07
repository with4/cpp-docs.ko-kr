---
title: 컴파일러 오류 C3641 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3641
dev_langs:
- C++
helpviewer_keywords:
- C3641
ms.assetid: e8d3613e-5e8d-46fe-a516-eb7d1de7cd21
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 496ff73822dcc1c886fbd2020f8ec6b8a5a9a2f7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3641"></a>컴파일러 오류 C3641
'function': 잘못 된 호출 규칙 'calling_convention' /clr을 사용 하 여 컴파일된 함수에 대 한: pure 또는 /clr: safe  
  
 **/clr:pure** 및 **/clr:safe** 컴파일러 옵션은 Visual Studio 2015에서는 더 이상 사용되지 않습니다.  
  
 만 [__clrcall](../../cpp/clrcall.md) 호출 규칙은 사용할 수 [/clr: pure](../../build/reference/clr-common-language-runtime-compilation.md)합니다.  
  
 다음 샘플에서는 C3641 오류가 생성 됩니다.  
  
```  
// C3641.cpp  
// compile with: /clr:pure /c  
void __cdecl f() {}   // C3641  
```