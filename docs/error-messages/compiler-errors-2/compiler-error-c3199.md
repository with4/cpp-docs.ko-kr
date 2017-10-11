---
title: "컴파일러 오류 C3199 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3199
dev_langs:
- C++
helpviewer_keywords:
- C3199
ms.assetid: e7a478d3-115a-40a3-991b-c7454fd2e28e
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 37443adbfdf65caba83656ca70ff799834fb4eac
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

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
