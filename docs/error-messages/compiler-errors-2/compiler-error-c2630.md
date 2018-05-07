---
title: 컴파일러 오류 C2630 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2630
dev_langs:
- C++
helpviewer_keywords:
- C2630
ms.assetid: 7a655a9c-bab4-495b-97a3-a3f34cf5369a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9a77a658f724f701e67968adb7a1310922b9476d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2630"></a>컴파일러 오류 C2630
'symbol' 기능에 쉼표로 구분 된 목록 이어야 합니다.  
  
 기호는 쉼표를 필요로 하는 컨텍스트에서 나타납니다.  
  
 다음 샘플에서는 C2630 오류가 생성 됩니다.  
  
```  
// C2630.cpp  
// compile with: /c  
struct D {  
   D(int);  
};  
  
struct E {  
   E(int);  
};  
  
class C : public D, public E {  
   C();  
};  
  
C::C() : D(0) ; E(0) { }   // C2630  
C::C() : D(0), E(0) {}   // OK  
```