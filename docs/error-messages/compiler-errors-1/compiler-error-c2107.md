---
title: "컴파일러 오류 C2107 | Microsoft Docs"
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
  - "C2107"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2107"
ms.assetid: 2866a121-884e-4bb5-8613-36de5817000e
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2107
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

인덱스가 잘못되어 간접 참조를 사용할 수 없습니다.  
  
 포인터가 아닌 식에 첨자가 적용되었습니다.  
  
## 예제  
 C2107은 형식의 기본 인덱서에 액세스하기 위해 값 형식의 `this` 포인터를 잘못 사용한 경우에 발생할 수 있습니다.  자세한 내용은 [this pointer의 의미체계](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Semantics_of_the_this_pointer)를 참조하십시오..  
  
 다음 샘플에서는 C2107 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2107.cpp  
// compile with: /clr  
using namespace System;  
  
value struct B {  
   property String ^ default[String ^] {  
      String ^ get(String ^ data) {  
         return "abc";  
      }  
   }  
   void Test() {  
      Console::WriteLine("{0}", this["aa"]);   // C2107  
      Console::WriteLine("{0}", this->default["aa"]);   // OK  
   }  
};  
  
int main() {  
   B ^ myb = gcnew B();  
   myb->Test();  
}  
```