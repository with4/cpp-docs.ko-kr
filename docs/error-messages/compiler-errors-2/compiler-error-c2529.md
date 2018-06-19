---
title: 컴파일러 오류 C2529 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2529
dev_langs:
- C++
helpviewer_keywords:
- C2529
ms.assetid: 73a99e55-b91e-488d-9b72-cc80faaeb436
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fb2d5de2375a243250b320ac313de4129795eb32
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33199757"
---
# <a name="compiler-error-c2529"></a>컴파일러 오류 C2529
'name': 참조에 대 한 참조가 잘못 되었습니다.  
  
 포인터 구문을 사용 하 고 포인터에 대 한 참조를 선언 하 여이 오류를 해결할 수 있습니다.  
  
 다음 샘플에서는 C2529 오류가 생성 됩니다.  
  
```  
// C2529.cpp  
// compile with: /c  
int i;  
int &ri = i;  
int &(&rri) = ri;   // C2529  
```