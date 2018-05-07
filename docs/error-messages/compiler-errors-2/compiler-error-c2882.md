---
title: 컴파일러 오류 C2882 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2882
dev_langs:
- C++
helpviewer_keywords:
- C2882
ms.assetid: 617018ee-5a0d-4b8d-9612-77e8ae52679b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d2885d00f31dbb9e057317e12b43b838579b33aa
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2882"></a>컴파일러 오류 C2882
'name': 식에서 네임 스페이스 식별자를 잘못 사용 했습니다.  
  
 식에 네임 스페이스 이름을 사용 하려고 했습니다.  
  
 다음 샘플에서는 C2882 오류가 생성 됩니다.  
  
```  
// C2882.cpp  
// compile with: /c  
namespace A {  
   int k;  
}  
  
int i = A;   // C2882, can't assign A to i  
```