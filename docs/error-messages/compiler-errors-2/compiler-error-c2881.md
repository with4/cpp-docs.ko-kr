---
title: 컴파일러 오류 C2881 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2881
dev_langs:
- C++
helpviewer_keywords:
- C2881
ms.assetid: b49c63c2-b064-4d4b-a75e-ddd2af947522
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 68be8efee689caab28c420d745bdfb59fb25f641
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2881"></a>컴파일러 오류 C2881
'namespace1': 이미 'namespace2'에 대 한 별칭으로 사용  
  
 두 개의 네임 스페이스에 대 한 별칭으로 동일한 이름을 사용할 수 없습니다.  
  
 다음 샘플에서는 C2881 오류가 생성 됩니다.  
  
```  
// C2881.cpp  
// compile with: /c  
namespace A {  
   int k;  
}  
  
namespace B {  
   int i;  
}  
  
namespace C = A;  
namespace C = B;   // C2881 C is already an alias for A  
```