---
title: "컴파일러 오류 C3754 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3754"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3754"
ms.assetid: 14b877bc-9277-40ec-af1c-196a58b45f10
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C3754
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

대리 생성자: 멤버 함수 'function'을\(를\) 'type' 형식의 인스턴스에 대해 호출할 수 없습니다.  
  
 함수를 포함하지 않는 형식에 대한 포인터를 통해 함수를 호출했습니다.  
  
 다음 샘플에서는 C3754 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3754a.cpp  
// compile with: /clr  
using namespace System;  
  
delegate void MyDel();  
  
interface class MyInterface {};  
  
ref struct MyClass : MyInterface {  
   void f() {}  
};  
  
int main() {  
   MyInterface^ p = gcnew MyClass;  
   MyDel^ q = gcnew MyDel(p, &MyClass::f);   // C3754  
   // try the following line instead  
//   MyDel^ q = gcnew MyDel(safe_cast<MyClass^>(p), &MyClass::f);  
}  
```  
  
 다음 샘플에서는 C3754 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3754b.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
using namespace System;  
  
__delegate void MyDel();  
  
__gc __interface MyInterface {};  
  
__gc struct MyClass : MyInterface {  
   void f() {}  
};  
  
int main() {  
   MyInterface* p = new MyClass;  
   MyDel* q = new MyDel(p, &MyClass::f);   // C3754  
   // try the following line instead  
   // MyDel* q = new MyDel(__try_cast<MyClass*>(p), &MyClass::f);  
}  
```