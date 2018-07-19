---
title: 컴파일러 경고 (수준 1) C4807 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4807
dev_langs:
- C++
helpviewer_keywords:
- C4807
ms.assetid: 089c9f87-fd81-402e-9826-66a8ef1ef1fe
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 22710ee2b46a270e46aed7c043d4d988fcfaed62
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33282365"
---
# <a name="compiler-warning-level-1-c4807"></a>컴파일러 경고(수준 1) C4807
'operation': 'type' 형식과 'type' 형식의 부호 있는 비트 필드를 함께 사용하는 것은 안전하지 않습니다.  
  
 이 경고는 1비트 부호 있는 비트 필드를 `bool` 변수와 비교할 때 생성됩니다. 1비트 부호 있는 비트 필드에는 -1 또는 0 값만 포함할 수 있으므로 `bool`과 비교하는 것은 위험합니다. 1비트 부호 없는 비트 필드는 `bool` 과 동일하며 0 또는 1만 포함할 수 있으므로 `bool` 과 함께 사용해도 경고가 생성되지 않습니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C4807을 생성합니다.  
  
```  
// C4807.cpp  
// compile with: /W1  
typedef struct bitfield {  
   signed mybit : 1;  
} mybitfield;  
  
int main() {  
   mybitfield bf;  
   bool b = true;  
  
   // try..  
   // int b = true;  
  
   bf.mybit = -1;  
   if (b == bf.mybit) {   // C4807  
      b = false;  
   }  
}  
```