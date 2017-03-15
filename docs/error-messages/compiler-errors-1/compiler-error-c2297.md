---
title: "컴파일러 오류 C2297 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2297"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2297"
ms.assetid: 65849fe5-17e1-4b7e-b50c-f508b05ddaa4
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C2297
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'operator' : 오른쪽 피연산자가 잘못되었습니다.  
  
 `operator`와 함께 사용된 오른쪽 피연산자가 잘못되었습니다.  
  
 예를 들어, 함수 호출이 필요한 위치에 함수를 선언한 경우일 수 있습니다.  
  
 다음 샘플에서는 C2297 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2297.cpp  
struct MyStruct {  
   struct Help {  
      Help(float f) : m_f(f) {}  
      float m_f;  
   };  
  
   MyStruct(const Help &h) : m_f(h.m_f) {}  
  
   MyStruct(float f) : m_f(f) {}  
  
   MyStruct operator*(const MyStruct &f1) const {   
      return MyStruct(m_f * f1.m_f);  
   }  
  
private:  
   float m_f;  
};  
  
int main() {  
   float f1 = 1.0f;  
  
   MyStruct m_MyStruct1 ( MyStruct::Help( f1 ) );  
   // try the following line instead  
   // MyStruct m_MyStruct1 = MyStruct::Help( f1 );  
  
   MyStruct m_MyStruct2 ( MyStruct::Help( f1 ) );  
   // try the following line instead  
   // MyStruct m_MyStruct2 = MyStruct::Help( f1 );  
  
   MyStruct m_MyStruct3 = m_MyStruct1 * m_MyStruct2;   // C2297  
}  
```