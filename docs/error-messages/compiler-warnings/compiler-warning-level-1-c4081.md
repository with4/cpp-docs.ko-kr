---
title: 컴파일러 경고 (수준 1) C4081 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4081
dev_langs:
- C++
helpviewer_keywords:
- C4081
ms.assetid: 6f656373-a080-4989-bbc9-e2f894b03293
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a55ee972e16655ab93ab463417718eb879ef2477
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4081"></a>컴파일러 경고(수준 1) C4081
'token1'이 필요한데 'token2'가 있습니다.  
  
 이 컨텍스트에서는 컴파일러에 다른 토큰이 필요합니다.  
  
## <a name="example"></a>예제  
  
```  
// C4081.cpp  
// compile with: /W1 /LD  
#pragma optimize) "l", on )   // C4081  
```