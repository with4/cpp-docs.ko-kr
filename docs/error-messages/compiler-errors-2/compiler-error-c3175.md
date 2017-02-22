---
title: "컴파일러 오류 C3175 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3175"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3175"
ms.assetid: 3f19d513-a05a-4b6c-806f-276fe5c36b90
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C3175
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function1' : 관리되는 형식의 메서드를 관리되지 않는 함수 'function2'에서 호출할 수 없습니다.  
  
 관리되지 않는 함수는 관리되는 클래스의 멤버 함수를 호출할 수 없습니다.  
  
 다음 샘플에서는 C3175 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3175_2.cpp  
// compile with: /clr  
  
ref struct A {  
   static void func() {  
   }  
};  
  
#pragma unmanaged   // remove this line to resolve  
  
void func2() {  
   A::func();   // C3175  
}  
  
#pragma managed  
  
int main() {  
   A ^a = gcnew A;  
   func2();  
}  
```  
  
 다음 샘플에서는 C3175 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3175.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
  
__gc struct A  
{  
   static void func()  
   {  
   }  
};  
  
#pragma unmanaged   // remove this line to resolve  
  
void func2()  
{  
   A::func();   // C3175  
}  
  
#pragma managed  
  
int main()  
{  
   A *a = new A;  
   func2();  
}  
```