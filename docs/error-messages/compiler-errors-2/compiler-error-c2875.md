---
title: 컴파일러 오류 C2875 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2875
dev_langs:
- C++
helpviewer_keywords:
- C2875
ms.assetid: d589fc0c-08b2-4a79-bc0e-dca5eb80bdd5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6b52ba86dccf5451c80c389d5726d81e2511ab31
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33243070"
---
# <a name="compiler-error-c2875"></a>컴파일러 오류 C2875
사용 하 여 선언 하면 'class::identifier'의 여러 선언  
  
 이 선언은 동일 항목을 두 번 정의 됩니다.  
  
 다음 샘플에서는 C2875 오류가 생성 됩니다.  
  
```  
// C2875.cpp  
struct A {  
   void f(int*);  
};  
  
struct B {  
   void f(double*);  
};  
  
struct AB : A, B {  
   using A::f;  
   using A::f;   // C2875  
   using B::f;  
};  
```