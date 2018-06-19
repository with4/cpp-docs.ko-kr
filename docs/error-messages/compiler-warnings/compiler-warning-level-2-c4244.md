---
title: 컴파일러 경고 (수준 2) C4244 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4244
dev_langs:
- C++
helpviewer_keywords:
- C4244
ms.assetid: 2c19d157-21d1-42c2-a6c0-3f30f2ce3813
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: de3b2392575f069c9ffc7b661cbd647f81f9557b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33290714"
---
# <a name="compiler-warning-level-2-c4244"></a>컴파일러 경고(수준 2) C4244
'argument': 'type1'에서 'type2', 데이터가 손실 될 수로 변환  
  
 A 부동 소수점 형식은 정수 형식으로 변환 합니다.  데이터 손실이 발생했을 수 있습니다.  
  
 C4244 오류가 발생하는 경우 호환되는 형식을 사용하도록 프로그램을 변경하거나 코드에 일부 논리를 추가하여 가능한 값의 범위가 사용 중인 형식과 항상 호환되는지 확인해야 합니다.  
  
 C4244 오류가 수준 3 및 4;에서 발생할 수도 있습니다. 참조 [컴파일러 경고 (수준 3 및 4) C4244](../../error-messages/compiler-warnings/compiler-warning-levels-3-and-4-c4244.md) 자세한 정보에 대 한 합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C4244 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4244_level2.cpp  
// compile with: /W2  
  
int f(int x){ return 0; }  
int main() {  
   double x = 10.1;  
   int i = 10;  
   return (f(x));   // C4244  
   // try the following line instead  
   // return (f(i));  
}  
```