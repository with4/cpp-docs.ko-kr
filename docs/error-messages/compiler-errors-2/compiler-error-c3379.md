---
title: "컴파일러 오류 C3379 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3379
dev_langs: C++
helpviewer_keywords: C3379
ms.assetid: a66c2c4e-091c-4426-9cde-7c4cfb2ffce1
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9fd5a8acf918a0f6b485cf9ba94ad759d58f7b2e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3379"></a>컴파일러 오류 C3379
'class': 중첩된 클래스 선언의 일부로 어셈블리 액세스 지정자를 사용할 수 없습니다  
  
 클래스 또는 구조체와 같은 관리 되는 형식에 적용 될 때는 [공용](../../cpp/public-cpp.md) 및 [개인](../../cpp/private-cpp.md) 키워드는 클래스가 어셈블리 메타 데이터를 통해 노출 될 지 여부를 나타냅니다. `public`또는 `private` 바깥쪽 클래스의 어셈블리 액세스 권한을 상속 합니다 중첩된 클래스에 적용할 수 없습니다.  
  
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
