---
title: "컴파일러 경고 (수준 1) C4441 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4441
dev_langs: C++
helpviewer_keywords: C4441
ms.assetid: 7fc540a5-e41f-47cf-aa37-b2b699c2685e
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 33337741819d908ce9445d82d905ecfc5738acda
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4441"></a>컴파일러 경고(수준 1) C4441
호출 규칙의 'cc1'가 무시 됩니다. ' cc2'를 대신 사용  
  
 관리 되는 사용자 정의 형식 및 전역 함수 제네릭 멤버 함수를 사용 해야 합니다는 [__clrcall](../../cpp/clrcall.md) 호출 규칙입니다.  사용 된 컴파일러 `__clrcall`합니다.  
  
## <a name="example"></a>예  
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