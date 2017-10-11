---
title: "컴파일러 오류 C3175 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3175
dev_langs:
- C++
helpviewer_keywords:
- C3175
ms.assetid: 3f19d513-a05a-4b6c-806f-276fe5c36b90
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: b2b8ff8052a9d54e12a4eca6a54701708096352a
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3175"></a>컴파일러 오류 C3175
'function1': 관리 되지 않는 함수 'function2'에서 관리 되는 형식의 메서드를 호출할 수 없습니다  
  
 관리 되지 않는 함수는 관리 되는 클래스의 멤버 함수를 호출할 수 없습니다.  
  
 다음 샘플에서는 C3175 오류가 생성 됩니다.  
  
```  
// C3175_2.cpp  
// compile with: /clr  
  
ref struct A {  
   static void func() {  
   }  
};  
  
#pragma unmanaged   // remove this line to resolve  
  
void func2() {  
   A::func();   // C3175  
}  
  
#pragma managed  
  
int main() {  
   A ^a = gcnew A;  
   func2();  
}  
```  

