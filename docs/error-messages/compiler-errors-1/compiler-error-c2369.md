---
title: 컴파일러 오류 C2369 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2369
dev_langs:
- C++
helpviewer_keywords:
- C2369
ms.assetid: 2a3933f6-2313-40ff-800f-921b296fdbbf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b1c97f8451e6807e6b78148a7027c37ccc967bd4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2369"></a>컴파일러 오류 C2369
'array': 재정의. 첨자가 다릅니다.  
  
 배열이 다른 아래 첨자로 이미 선언되었습니다.  
  
 다음 샘플에서는 C2369를 생성합니다.  
  
```  
// C2369.cpp  
// compile with: /c  
int a[10];  
int a[20];   // C2369  
int b[20];   // OK  
```