---
title: "컴파일러 오류 C3915 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3915"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3915"
ms.assetid: 2b0a5e5f-3aec-4a4b-9157-233031817084
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 오류 C3915
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type'에 인덱싱된 기본 속성\(클래스 인덱서\)이 없습니다.  
  
 형식에 인덱싱된 기본 속성이 없습니다.  
  
 자세한 내용은 [속성](../../windows/property-cpp-component-extensions.md)을 참조하십시오.  
  
## 예제  
 다음 샘플에서는 C3915 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3915.cpp  
// compile with: /clr  
ref class X {  
public:  
// uncomment property to resolve this C3915  
//   property int default[]  
//   {  
//      int get(int i)  
//      {  
//         return 863;  
//      }  
//   }  
};  
  
int main() {  
   X^ x = new X;  
   System::Console::WriteLine(x[1]);   // C3915  
}  
```  
  
## 예제  
 C3915는 <xref:System.Reflection.DefaultMemberAttribute>를 사용하여 정의한 컴파일 대상에서 기본 인덱서를 사용하려는 경우에도 발생할 수 있습니다.  
  
 다음 샘플에서는 C3915 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3915_b.cpp  
// compile with: /clr  
using namespace System;  
  
[Reflection::DefaultMember("XXX")]  
ref struct A {  
   property Double XXX[Double] {  
      Double get(Double data) {  
         return data*data;  
      }  
   }  
};  
  
ref struct B {  
   property Double default[Double] {  
      Double get(Double data) {  
         return data*data;  
      }  
   }  
};  
  
int main() {  
   A ^ mya = gcnew A();  
   Console::WriteLine("{0}", mya[3]);   // C3915  
  
   B ^ myb = gcnew B();  
   Console::WriteLine("{0}", myb[3]);   // OK  
}  
```