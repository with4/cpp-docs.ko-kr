---
title: 컴파일러 오류 C3389 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3389
dev_langs:
- C++
helpviewer_keywords:
- C3389
ms.assetid: eaaffe17-23f2-413c-b1ad-f7220cfa1334
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6f0f60a1096c070d28be3b7af161bbb924fb20dd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3389"></a>컴파일러 오류 C3389
/clr을 사용한 __declspec(keyword)를 사용할 수 없습니다: pure 또는 /clr: safe  
  
 **/clr:pure** 및 **/clr:safe** 컴파일러 옵션은 Visual Studio 2015에서는 더 이상 사용되지 않습니다.  
  
 A [__declspec](../../cpp/declspec.md) 사용 되는 한정자 의미는 당 프로세스 상태입니다.  [/clr: pure](../../build/reference/clr-common-language-runtime-compilation.md) 의미는 당 [appdomain](../../cpp/appdomain.md) 상태입니다.  따라서 사용 하 여 변수를 선언에서 `keyword` **__declspec** 한정자와 사용 하 여 컴파일할 **/clr: 순수** 허용 되지 않습니다.  
  
 다음 샘플에서는 C3389 오류가 생성 됩니다.  
  
```  
// C3389.cpp  
// compile with: /clr:pure /c  
__declspec(dllexport) int g2 = 0;   // C3389  
```