---
title: 컴파일러 오류 C3199 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3199
dev_langs:
- C++
helpviewer_keywords:
- C3199
ms.assetid: e7a478d3-115a-40a3-991b-c7454fd2e28e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cddad2218e81603f59cad51e3a684303e144171e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3199"></a>컴파일러 오류 C3199
부동 소수점 pragma 잘못 사용 했습니다.: 예외가 명확 하지 않은 모드에서 지원 되지 않습니다  
  
 [float_control](../../preprocessor/float-control.md) pragma에서 부동 소수점 예외 모델을 지정 하는 데 사용한는 [/fp](../../build/reference/fp-specify-floating-point-behavior.md) 아닌 다른 설정을 **/fp: 정확한**합니다.  
  
 다음 샘플에서는 C3199 오류가 생성 됩니다.  
  
```  
// C3199.cpp  
// compile with: /fp:fast  
#pragma float_control(except, on)   // C3199  
```