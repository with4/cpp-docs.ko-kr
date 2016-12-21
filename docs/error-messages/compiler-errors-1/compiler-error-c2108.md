---
title: "컴파일러 오류 C2108 | Microsoft Docs"
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
  - "C2108"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2108"
ms.assetid: c84f0b47-5e2c-47d2-8edb-427a40e17c36
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2108
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

첨자가 정수 계열 형식이 아닙니다.  
  
 배열 첨자가 비정수 계열 식입니다.  
  
## 예제  
 C2107은 형식의 기본 인덱서에 액세스하기 위해 값 형식의 `this` 포인터를 잘못 사용한 경우에 발생할 수 있습니다.  자세한 내용은 [this pointer의 의미체계](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Semantics_of_the_this_pointer)를 참조하십시오..  
  
 다음 샘플에서는 C2108 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2108.cpp  
// compile with: /clr  
using namespace System;  
  
value struct B {  
   property Double default[Double] {  
      Double get(Double data) {  
         return data*data;  
      }  
   }  
   void Test() {  
      Console::WriteLine("{0}", this[3.3]);   // C2108  
      Console::WriteLine("{0}", this->default[3.3]);   // OK  
   }  
};  
  
int main() {  
   B ^ myb = gcnew B();  
   myb->Test();  
}  
```