---
title: "컴파일러 경고 (수준 1) C4947 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4947
dev_langs: C++
helpviewer_keywords: C4947
ms.assetid: 5a1d484e-b4c7-4de2-a145-d8dcfc2fc1d2
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e24b2ec34c81152088bf2e9cee73237dfa43b41b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4947"></a>컴파일러 경고(수준 1) C4947
'type_or_member': 사용되지 않는 것으로 표시되었습니다.  
  
멤버 또는 형식이 <xref:System.ObsoleteAttribute> 클래스에서 사용되지 않는 것으로 표시되었습니다.  
  
## <a name="example"></a>예  
다음 샘플에서는 C4947을 생성합니다.  
  
```cpp  
// C4947.cpp  
// compile with: /clr /W1  
// C4947 expected  
using namespace System;  
  
[System::ObsoleteAttribute]  
ref struct S {  
   [System::ObsoleteAttribute]  
   int i;  
  
   [System::ObsoleteAttribute]  
   void mFunc(){}  
};  
  
// Any reference to Func1 should generate a warning  
[System::ObsoleteAttribute]  
Int32 Func1(Int32 a, Int32 b) {  
   return (a + b);  
}  
  
// Any reference to Func2 should generate a warning with  message  
[System::ObsoleteAttribute("Will be removed in next version")]  
Int32 Func2(Int32 a, Int32 b) {  
   return (a + b);  
}  
  
int main() {  
   Int32 MyInt1 = ::Func1(2, 2);  
   Int32 MyInt2 = ::Func2(2, 2);  
  
   S^ s = gcnew S();  
   s->i = 10;  
   s->mFunc();  
}  
```