---
title: "컴파일러 오류 C2676 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2676"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2676"
ms.assetid: 838a5e34-c92f-4f65-a597-e150bf8cf737
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2676
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이항 'operator' : 'type'이\(가\) 이 연산자를 정의하지 않거나 미리 정의된 연산자에 허용되는 형식으로의 변환을 정의하지 않습니다.  
  
 연산자를 사용하려면 연산자를 지정된 형식에 대해 오버로드하거나 연산자에 정의된 형식으로 변환을 정의해야 합니다.  
  
## 예제  
 다음 샘플에서는 C2676 오류가 발생하는 경우를 보여 줍니다.  
  
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
  
## 예제  
 참조 형식의 `this` 포인터에 포인터 연산을 시도하는 경우에도 C2676이 발생할 수 있습니다.  
  
 참조 형식에서 `this` 포인터는 핸들 형식입니다.  자세한 내용은 [this pointer의 의미체계](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Semantics_of_the_this_pointer) 를 참조하십시오.  
  
 다음 샘플에서는 C2676 오류가 발생하는 경우를 보여 줍니다.  
  
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