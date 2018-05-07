---
title: 컴파일러 오류 C2850 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2850
dev_langs:
- C++
helpviewer_keywords:
- C2850
ms.assetid: f3efe86c-4168-4e76-a133-3f8314c69f51
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8e53f54aee2acdd163de0195c7475049fe2d6346
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2850"></a>컴파일러 오류 C2850
'construct': 파일 범위 에서만 사용할 수 중첩된 된 구문에 사용할 수 없습니다.  
  
 구문 예: 일부 pragma는 전역 범위에만 사용할 수 있습니다.  
  
 다음 샘플에서는 C2850 오류가 생성 됩니다.  
  
```  
// C2850.cpp  
// compile with: /c /Yc  
// try the following line instead  
// #pragma hdrstop  
namespace X {  
   #pragma hdrstop   // C2850  
};  
```