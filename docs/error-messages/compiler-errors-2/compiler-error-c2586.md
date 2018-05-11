---
title: 컴파일러 오류 C2586 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2586
dev_langs:
- C++
helpviewer_keywords:
- C2586
ms.assetid: dae703c7-5c38-4db6-8411-4d1b22713eb5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3cf21a9379f7b0d07575dae54d9406eb5cf39094
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2586"></a>컴파일러 오류 C2586
잘못 된 사용자 정의 변환 구문이: 간접 참조가 잘못 되었습니다  
  
 변환 연산자의 간접 참조는 허용 되지 않습니다.  
  
 다음 샘플에서는 C2586 오류가 생성 됩니다.  
  
```  
// c2586.cpp  
// compile with: /c  
struct C {  
   * operator int();   // C2586  
   operator char();   // OK  
};  
```