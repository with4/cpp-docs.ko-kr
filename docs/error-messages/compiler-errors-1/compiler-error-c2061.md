---
title: "컴파일러 오류 C2061 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2061"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2061"
ms.assetid: b0e61c0c-a205-4820-b9aa-301d6c6fe6eb
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# 컴파일러 오류 C2061
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

구문 오류 : 식별자 'identifier'  
  
 컴파일러가 예기치 못했던 식별자를 발견했습니다.  `identifier`를 사용하기 전에 이를 선언했는지 확인하십시오.  
  
 이니셜라이저를 괄호로 묶어야 할 수도 있습니다.  이 문제를 방지하려면 선언자를 괄호로 묶거나 `typedef`로 만드십시오.  
  
 컴파일러에서 식을 클래스 템플릿 인수로 인식할 때에도 이 오류가 발생할 수 있습니다. 이 경우 [typename](../../cpp/typename.md)을 사용하여 해당 식이 형식이라는 것을 나타내십시오.  
  
 다음 샘플에서는 C2061 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2061.cpp  
// compile with: /c  
template < A a >   // C2061  
// try the following line instead  
// template < typename b >  
class c{};  
```  
  
 C2061은 인스턴스 이름을 [typeid](../../windows/typeid-cpp-component-extensions.md)에 전달하는 경우 발생할 수 있습니다.  
  
```  
// C2061b.cpp  
// compile with: /clr  
ref struct G {  
   int i;  
};  
  
int main() {  
   G ^ pG = gcnew G;  
   System::Type ^ pType = typeid<pG>;   // C2061  
   System::Type ^ pType2 = typeid<G>;   // OK  
}  
```