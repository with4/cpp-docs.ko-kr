---
title: 컴파일러 오류 C2473 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2473
dev_langs:
- C++
helpviewer_keywords:
- C2473
ms.assetid: 6bb7dbf5-b198-490f-860e-fd64d0c2a284
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: af0342d3e8e6011e37b0588515299f2a0ab7b761
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2473"></a>컴파일러 오류 C2473
'identifier': 함수 정의로 보이지만 매개 변수 목록이 없습니다.  
  
 컴파일러가 매개 변수 목록 없이 함수처럼 보이는 항목을 발견했습니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C2473을 생성합니다.  
  
```  
// C2473.cpp  
// compile with: /clr /c  
class A {  
   int i {}   // C2473  
};  
  
class B {  
   int i() {}   // OK  
};  
```