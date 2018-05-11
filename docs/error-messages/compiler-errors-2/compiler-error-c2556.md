---
title: 컴파일러 오류 C2556 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2556
dev_langs:
- C++
helpviewer_keywords:
- C2556
ms.assetid: fc4399ad-45b3-49fd-be1f-0b13956a595a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: eb090b932daa93c2c680d4ec871b36c78f09a7c3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2556"></a>컴파일러 오류 C2556
'identifier': 오버 로드 된 함수의 반환 형식 그만 다릅니다.  
  
 오버 로드 된 함수 반환 형식은 각기 다르지만 동일한 매개 변수 목록을 갖고 있습니다. 각 오버 로드 된 함수에는 고유한 형식 매개 변수 목록이 있어야 합니다.  
  
 다음 샘플에서는 C2556 오류가 생성 됩니다.  
  
```  
// C2556.cpp  
// compile with: /c  
class C {  
   int func();  
   double func();   // C2556  
   int func(int i);   // ok parameter lists differ  
};  
```