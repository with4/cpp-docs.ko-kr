---
title: 컴파일러 경고 (수준 1) C4441 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4441
dev_langs:
- C++
helpviewer_keywords:
- C4441
ms.assetid: 7fc540a5-e41f-47cf-aa37-b2b699c2685e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6c2abf64be0e9b80bb4158b0ed163906adc09945
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33278231"
---
# <a name="compiler-warning-level-1-c4441"></a>컴파일러 경고(수준 1) C4441
호출 규칙의 'cc1'가 무시 됩니다. ' cc2'를 대신 사용  
  
 관리 되는 사용자 정의 형식 및 전역 함수 제네릭 멤버 함수를 사용 해야 합니다는 [__clrcall](../../cpp/clrcall.md) 호출 규칙입니다.  사용 된 컴파일러 `__clrcall`합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C4441 오류가 발생 합니다.  
  
```  
// C4441.cpp  
// compile with: /clr /W1 /c  
generic <class ItemType>  
void __cdecl Test(ItemType item) {}   // C4441  
// try the following line instead  
// void Test(ItemType item) {}  
  
ref struct MyStruct {  
   void __cdecl Test(){}   // C4441  
   void Test2(){}   // OK  
};  
```