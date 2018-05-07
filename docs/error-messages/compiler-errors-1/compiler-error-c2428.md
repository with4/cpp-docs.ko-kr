---
title: 컴파일러 오류 C2428 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2428
dev_langs:
- C++
helpviewer_keywords:
- C2428
ms.assetid: 74aa5714-e930-4f9e-9061-68ccce7f0d38
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2468e20265de6558464a493f49439f1766effa5b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2428"></a>컴파일러 오류 C2428
'operation': 'bool' 형식의 피연산자에 사용할 수 없습니다  
  
 형식의 개체에 감소 연산자를 적용할 수 없습니다 `bool`합니다.  
  
 다음 샘플에서는 C2428 오류가 생성 됩니다.  
  
```  
// C2428.cpp  
void g(bool fFlag) {  
   --fFlag;   // C2428  
   fFlag--;   // C2428  
}  
```