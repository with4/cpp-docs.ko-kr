---
title: 컴파일러 오류 C2594 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2594
dev_langs:
- C++
helpviewer_keywords:
- C2594
ms.assetid: 68cd708f-266e-44b0-a211-3e3ab63b11bf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9b1de853b8992d3c02eb94c0b050d72539fc3282
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2594"></a>컴파일러 오류 C2594
'operator': 'type1'에서 'type2'의 모호한 변환입니다.  
  
 변환 작업 없이 *type1* 를 *type2* 다른 것 보다 직접적 합니다. 변환에 두 가지 가능한 해결 방법을 제안 *type1* 를 *type2*합니다. 직접 변환을 정의 하 고 첫 번째 옵션은 *type1* 를 *type2*, 두 번째 옵션은 변환할 때의 시퀀스를 지정 하 고 *type1* 를  *유형 2*합니다.  
  
 다음 샘플에서는 C2594 오류가 발생 합니다. 오류에는 권장된 해결 방법을 변환의 순서.  
  
```  
// C2594.cpp  
// compile with: /c  
struct A{};  
struct I1 : A {};  
struct I2 : A {};  
struct D : I1, I2 {};  
  
A *f (D *p) {  
   return (A*) (p);    // C2594  
  
// try the following line instead  
// return static_cast<A *>(static_cast<I1 *>(p));  
}  
```