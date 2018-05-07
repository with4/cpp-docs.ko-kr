---
title: 컴파일러 경고 (수준 1) C4163 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4163
dev_langs:
- C++
helpviewer_keywords:
- C4163
ms.assetid: b08413fd-03fc-4f41-9167-a98976ac12f2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d39297a17c5e7c7b6b95fd0e43f33849c092fa1d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4163"></a>컴파일러 경고(수준 1) C4163
'identifier': 내장 함수로 사용할 수 없습니다.  
  
 지정된 함수를 [intrinsic](../../preprocessor/intrinsic.md) 함수로 사용할 수 없습니다. 컴파일러에서 잘못된 함수 이름은 무시합니다.  
  
 다음 샘플에서는 C4163을 생성합니다.  
  
```  
// C4163.cpp  
// compile with: /W1 /LD  
#include <math.h>  
#pragma intrinsic(mysin)   // C4163  
// try the following line instead  
// #pragma intrinsic(sin)  
```