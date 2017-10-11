---
title: "컴파일러 오류 C3198 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3198
dev_langs:
- C++
helpviewer_keywords:
- C3198
ms.assetid: ec4ecf61-0067-4aa4-b443-a91013a1e59d
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 56325b1410e2d7255eec599cdb73f52710bbe1c1
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3198"></a>컴파일러 오류 C3198
부동 소수점 pragma 잘못 사용 했습니다: fenv_access pragma는 precise 모드 에서만에서 작동  
  
 [fenv_access](../../preprocessor/fenv-access.md) pragma에서 사용한는 [/fp](../../build/reference/fp-specify-floating-point-behavior.md) 아닌 다른 설정을 **/fp: 정확한**합니다.  
  
 다음 샘플에서는 C3198 오류가 생성 됩니다.  
  
```  
// C3198.cpp  
// compile with: /fp:fast  
#pragma fenv_access(on)   // C3198  
```
