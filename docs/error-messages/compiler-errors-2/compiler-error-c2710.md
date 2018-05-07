---
title: 컴파일러 오류 C2710 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2710
dev_langs:
- C++
helpviewer_keywords:
- C2710
ms.assetid: a2a6bb5b-86ad-4a6c-acd0-e2bef8464e0e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bfc182527aeb349fb91d098133c4545b95a93ac2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2710"></a>컴파일러 오류 C2710
'construct': '__declspec(modifier)' 포인터를 반환 하는 함수에만 적용할 수 있습니다  
  
 반환 값이 함수는 있는 유일한 구문 `modifier` 적용 될 수 있습니다.  
  
 다음 샘플에서는 C2710 오류가 생성 됩니다.  
  
```  
// C2710.cpp  
__declspec(restrict) void f();   // C2710  
// try the following line instead  
__declspec(restrict) int * g();  
```