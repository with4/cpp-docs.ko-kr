---
title: 컴파일러 오류 C2635 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2635
dev_langs:
- C++
helpviewer_keywords:
- C2635
ms.assetid: 9deca2a8-2d61-42eb-9783-6578132ee3fb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 30916834b8adee0d1a80625624e80c5a860e57ae
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33233992"
---
# <a name="compiler-error-c2635"></a>컴파일러 오류 C2635
변환할 수 없습니다는 ' identifier1 *'는 ' identifier2\*'; 암시 가상 기본 클래스에서 변환  
  
 변환에서 캐스트에 필요 하지만 `virtual` 기본 클래스에 파생된 클래스는 허용 되지 않습니다.  
  
 다음 샘플에서는 C2635 오류가 생성 됩니다.  
  
```  
// C2635.cpp  
class B {};  
class D : virtual public B {};  
class E : public B {};  
  
int main() {  
   B b;  
   D d;  
   E e;  
  
   D * pD = &d;  
   E * pE = &e;  
   pD = (D*)&b;   // C2635  
   pE = (E*)&b;   // OK  
}  
```