---
title: 컴파일러 경고 (수준 2) C4307 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4307
dev_langs:
- C++
helpviewer_keywords:
- C4307
ms.assetid: 7cca11e9-be61-49e4-8b15-88b84f0cbf07
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 52914fc5825bda5647308c006b853538f3d6225e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-2-c4307"></a>컴파일러 경고(수준 2) C4307
'operator': 정수 계열 상수 오버플로입니다  
  
 연산자는 정수 계열 상수에 할당 된 공간 오버플로가 발생 하는 식에 사용 됩니다. 상수에 대해 더 큰 형식을 사용 해야 합니다. A **int 서명** 보다 작은 값을 저장 한 `unsigned int` 때문에 **int 서명** 1 비트가 부호를 사용 하 여 합니다.  
  
 다음 샘플에서는 C4307 오류가 생성 됩니다.  
  
```  
// C4307.cpp  
// compile with: /W2  
int i = 2000000000 + 2000000000;   // C4307  
int j = (unsigned)2000000000 + 2000000000;   // OK  
  
int main()  
{  
}  
```