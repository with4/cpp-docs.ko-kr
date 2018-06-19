---
title: 컴파일러 경고 (수준 4) C4343 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4343
dev_langs:
- C++
helpviewer_keywords:
- C4343
ms.assetid: a721b710-e04f-4d15-b678-e4a2c8fd0181
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 300bab652c88322ef7e3b28cbf2cafe304d361d5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33302336"
---
# <a name="compiler-warning-level-4-c4343"></a>컴파일러 경고(수준 4) C4343
\#pragma optimize("g",off) /Og 옵션을 재정의합니다.  
  
 이 경고는 IPF(Itanium Processor Family) 컴파일러에서만 사용되며 pragma [optimize](../../preprocessor/optimize.md) 가 [/Og](../../build/reference/og-global-optimizations.md) 컴파일러 옵션을 재정의했음을 보고합니다.  
  
 다음 샘플에서는 C4343을 생성합니다.  
  
```  
// C4343.cpp  
// compile with: /Og /W4 /LD  
// processor: IPF  
#pragma optimize ("g", off)   // C4343  
```