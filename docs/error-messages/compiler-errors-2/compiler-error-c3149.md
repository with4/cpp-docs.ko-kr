---
title: "컴파일러 오류 C3149 | Microsoft Docs"
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
  - "C3149"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3149"
ms.assetid: cf6e2616-2f06-46da-8a8a-d449cb481c51
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3149
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : 여기에 이 형식을 사용하려면 최상위 'char'이\(가\) 있어야 합니다.  
  
 선언을 올바르게 지정하지 않았습니다.  
  
 예를 들어, 전역 범위에서 CLR 형식을 정의하고 이 형식의 변수를 정의의 일부로 만들려고 했습니다.  CLR 형식의 전역 변수는 허용되지 않으므로 컴파일러에서 C3149가 발생합니다.  
  
 이 오류를 해결하려면 함수나 형식 정의 안에서 CLR 형식의 변수를 선언해야 합니다.  
  
 다음 샘플에서는 C3149 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3149.cpp  
// compile with: /clr  
using namespace System;  
int main() {  
   // declare an array of value types   
   array< Int32 ^> IntArray;   // C3149  
   array< Int32>^ IntArray2;   // OK  
}  
```  
  
 다음 샘플에서는 C3149 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3149b.cpp  
// compile with: /clr /c  
delegate int MyDelegate(const int, int);  
void Test1(MyDelegate m) {}   // C3149  
void Test2(MyDelegate ^ m) {}   // OK  
```  
  
 **Managed Extensions for C\+\+**  
  
 관리되는 개체를 올바르게 사용하지 않았습니다.  
  
 다음 샘플에서는 C3149 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3149c.cpp  
// compile with: /clr:oldSyntax  
__gc class A {};  
  
int main() {  
   A a = new A;   // C3149  
   A *a = new A;   // OK  
}  
```