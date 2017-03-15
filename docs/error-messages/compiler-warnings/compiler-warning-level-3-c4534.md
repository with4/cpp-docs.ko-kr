---
title: "컴파일러 경고 (수준 3) C4534 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "c4534"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4534"
ms.assetid: ec2adf3b-d7a1-4005-bb0c-5d219df78dc8
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 경고 (수준 3) C4534
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'constructor'은\(는\) 기본 인수 때문에 클래스 'class'에 대한 기본 생성자가 되지 못합니다.  
  
 관리되지 않는\` 클래스에는 기본값이 있는 매개 변수를 사용하는 생성자가 있고 컴파일러에서 이를 기본 생성자로 사용합니다.  `value` 키워드로 표시된 클래스는 매개 변수에 기본값이 있는 생성자를 기본 생성자로 사용하지 않습니다.  
  
 자세한 내용은 [Classes and Structs](../../windows/classes-and-structs-cpp-component-extensions.md)을 참조하십시오.  
  
 다음 샘플에서는 C4534 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4534.cpp  
// compile with: /W3 /clr /WX  
value class MyClass {  
public:  
   int ii;  
   MyClass(int i = 9) {   // C4534, will not be the default constructor  
      i++;  
   }  
};  
  
int main() {  
   MyClass ^ xx = gcnew MyClass;  
   xx->ii = 0;  
}  
```