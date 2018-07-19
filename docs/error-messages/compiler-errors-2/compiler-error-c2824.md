---
title: 컴파일러 오류 C2824 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2824
dev_langs:
- C++
helpviewer_keywords:
- C2824
ms.assetid: 5bd865f7-e0af-404e-80fe-e2b798b44a59
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bc654f60d9494480e0551f4de3ec1e041938cea2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33237166"
---
# <a name="compiler-error-c2824"></a>컴파일러 오류 C2824
'operator new' 이어야 합니다 반환 형식은 ' void *'  
  
 연산자 오버 로드 아닌 기반 포인터 `new` 반환 해야 `void *`합니다.  
  
 다음 샘플에서는 C2824 오류가 생성 됩니다.  
  
```  
// C2824.cpp  
// compile with: /c  
class   A {  
   A* operator new(size_t i, char *m);   // C2824  
   // try the following line instead  
   // void* operator new(size_t i, char *m);  
};  
```