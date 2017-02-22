---
title: "컴파일러 오류 C3185 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3185"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3185"
ms.assetid: 5bf96279-043c-4981-9d02-b4550071b192
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# 컴파일러 오류 C3185
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'typeid' : 관리되는 형식 또는 WinRT 형식 'type'에 사용되었습니다. 대신 'operator'를 사용하세요.  
  
 관리되는 형식 또는 WinRT 형식에 [typeid](../../cpp/typeid-operator.md) 연산자를 적용할 수 없습니다. 대신 [typeid](../../windows/typeid-cpp-component-extensions.md)를 사용하세요.  
  
 다음 샘플에서는 C3185 오류가 발생하는 경우 및 이를 해결하는 방법을 보여 줍니다.  
  
```  
// C3185a.cpp  
// compile with: /clr  
ref class Base {};  
ref class Derived : public Base {};  
  
int main() {  
   Derived ^ pd = gcnew Derived;  
   Base ^pb = pd;  
   const type_info & t1 = typeid(pb);   // C3185  
   System::Type ^ MyType = Base::typeid;   // OK  
};  
```  
  
 **Managed Extensions for C\+\+**  
  
 관리되는 형식에 [typeid](../../cpp/typeid-operator.md)를 적용할 수 없습니다. 대신 [\_\_typeof](../../misc/typeof.md)를 사용하세요.  
  
 다음 샘플에서는 C3185 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3185b.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
__gc class Base {};  
__gc class Derived : public Base {};  
  
int main() {  
   Derived *pd = new Derived;  
   Base *pb = pd;  
   const type_info & t1 = typeid(*pb);   // C3185  
  
   // OK  
   Type * t = __typeof(Base);  
   Type * t1 = __typeof(Derived);  
};  
```