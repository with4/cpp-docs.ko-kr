---
title: 컴파일러 오류 C3609 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3609
dev_langs:
- C++
helpviewer_keywords:
- C3609
ms.assetid: 801e7f79-4ac6-4f8f-955f-703cdf095d00
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7b0f3ec99e5d528967fb7b02bc9d198402b16e18
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33258298"
---
# <a name="compiler-error-c3609"></a>컴파일러 오류 C3609
'member': 봉인 함수 또는 최종 함수는 virtual이어야 합니다.  
  
 [봉인](../../windows/sealed-cpp-component-extensions.md) 및 [최종](../../cpp/final-specifier.md) 키워드는 표시 된 클래스, 구조체 또는 멤버 함수에만 사용할 수 `virtual`합니다.  
  
 다음 샘플에서는 C3609 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3609.cpp  
// compile with: /clr /c  
ref class C {  
   int f() sealed;   // C3609  
   virtual int f2() sealed;   // OK  
};  
```  
