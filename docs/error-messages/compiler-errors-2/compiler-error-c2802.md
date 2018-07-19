---
title: 컴파일러 오류 C2802 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2802
dev_langs:
- C++
helpviewer_keywords:
- C2802
ms.assetid: 08b68c0e-9382-40ac-8949-39a7a2749e05
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fe069b93c8dc6bb098927925e93f10cec2dbc4c3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33236659"
---
# <a name="compiler-error-c2802"></a>컴파일러 오류 C2802
정적 멤버 'operator 연산자'에 정식 매개 변수가 없습니다.  
  
 선언한 연산자는 `static` 멤버 함수는 매개 변수가 하나 이상 있어야 합니다.  
  
 다음 샘플에서는 C2802 오류가 생성 됩니다.  
  
```  
// C2802.cpp  
// compile with: /clr /c  
ref class A {  
   static operator+ ();   // C2802  
   static operator+ (A^, A^);   // OK  
};  
```