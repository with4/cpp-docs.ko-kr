---
title: "컴파일러 오류 C3379 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3379
dev_langs:
- C++
helpviewer_keywords:
- C3379
ms.assetid: a66c2c4e-091c-4426-9cde-7c4cfb2ffce1
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: 16c62e48a0190096e04dc4ccf0c17ca66c2f4094
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3379"></a>컴파일러 오류 C3379
'class': 중첩된 클래스 선언의 일부로 어셈블리 액세스 지정자를 사용할 수 없습니다  
  
 클래스 또는 구조체와 같은 관리 되는 형식에 적용 된 경우는 [공용](../../cpp/public-cpp.md) 및 [개인](../../cpp/private-cpp.md) 키워드는 클래스 어셈블리 메타 데이터를 통해 노출 될 있는지 여부를 나타냅니다. `public`또는 `private` 바깥쪽 클래스의 어셈블리 액세스 권한을 상속 하는 중첩된 클래스에 적용할 수 없습니다.  
  
 와 함께 사용할 경우 [/clr](../../build/reference/clr-common-language-runtime-compilation.md), `ref` 및 `value` 키워드 관리 되는 클래스를 나타냅니다 (참조 [클래스 및 구조체](../../windows/classes-and-structs-cpp-component-extensions.md)).  
  
 다음 샘플에서는 C3379 오류가 생성 됩니다.  
  
```  
// C3379a.cpp  
// compile with: /clr  
using namespace System;  
  
public ref class A {  
public:  
   static int i = 9;  
  
   public ref class BA {   // C3379  
   // try the following line instead  
   // ref class BA {  
   public:  
      static int ii = 8;  
   };  
};  
  
int main() {  
  
   A^ myA = gcnew A;  
   Console::WriteLine(myA->i);  
  
   A::BA^ myBA = gcnew A::BA;  
   Console::WriteLine(myBA->ii);  
}  
```  

