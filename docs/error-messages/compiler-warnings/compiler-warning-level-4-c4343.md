---
title: "컴파일러 경고 (수준 4) C4343 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4343
dev_langs:
- C++
helpviewer_keywords:
- C4343
ms.assetid: a721b710-e04f-4d15-b678-e4a2c8fd0181
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: a67b44c766f51acb7a9d4cacc94448f1b4594c3e
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-4-c4343"></a>컴파일러 경고(수준 4) C4343
\#pragma optimize("g",off) /Og 옵션을 재정의합니다.  
  
 이 경고는 제품군 IPF (Itanium Processor) 컴파일러에서 유효한 것으로 보고 되는 pragma [최적화](../../preprocessor/optimize.md) 가 [/Og](../../build/reference/og-global-optimizations.md) 컴파일러 옵션입니다.  
  
 다음 샘플에서는 C4343을 생성합니다.  
  
```  
// C4343.cpp  
// compile with: /Og /W4 /LD  
// processor: IPF  
#pragma optimize ("g", off)   // C4343  
```
