---
title: "컴파일러 오류 C2676 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2676
dev_langs:
- C++
helpviewer_keywords:
- C2676
ms.assetid: 838a5e34-c92f-4f65-a597-e150bf8cf737
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fad1dce3ca6b707ab8e9e687a5c31b4ecb49d411
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2676"></a>컴파일러 오류 C2676
이항 'operator': 'type' 정의 하지 않습니다이 연산자 또는 허용 되는 형식으로의 변환을 미리 정의 된 연산자  
  
 연산자를 사용하려면 지정된 형식에 대해 오버로드하거나 연산자가 정의된 형식으로의 변환을 정의해야 합니다.  
  
## <a name="example"></a>예  
 다음 샘플에서는 C2676 오류가 발생 합니다.  
  
```  
// C2676.cpp  
// C2676 expected  
struct C {  
   C();  
} c;  
  
struct D {  
   D();  
   D operator >>( C& ){return * new D;}  
   D operator <<( C& ){return * new D;}  
} d;  
  
struct E {  
   // operator int();  
};  
  
int main() {  
   d >> c;  
   d << c;  
   E e1, e2;  
   e1 == e2;   // uncomment operator int in class E, then  
               // it is OK even though neither E::operator==(E) nor   
               // operator==(E, E) defined. Uses the conversion to int   
               // and then the builtin-operator==(int, int)  
}  
```  
  
## <a name="example"></a>예  
 포인터 산술 연산을 수행 하려는 경우에 C2676 발생할 수 있습니다는 `this` 참조 형식의 포인터입니다.  
  
 `this` 포인터는 참조 형식에서 형식 핸들입니다. 자세한 내용은 참조 [this의 의미 체계 포인터](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Semantics_of_the_this_pointer)합니다.  
  
 다음 샘플에서는 C2676 오류가 발생 합니다.  
  
```  
// C2676_a.cpp  
// compile with: /clr  
using namespace System;  
  
ref struct A {  
   property Double default[Double] {  
      Double get(Double data) {  
         return data*data;  
      }  
   }  
  
   A() {  
      Console::WriteLine("{0}", this + 3.3);   // C2676  
      Console::WriteLine("{0}", this[3.3]);   // OK  
   }  
};  
  
int main() {  
   A ^ mya = gcnew A();  
}  
```