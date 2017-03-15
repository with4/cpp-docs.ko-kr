---
title: "방법: 네이티브 컴파일에 override 지정자 선언(C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "네이티브 컴파일의 override 지정자, 재정의"
ms.assetid: d0551836-9ac7-41eb-a6e9-a4b3ef60767d
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: 네이티브 컴파일에 override 지정자 선언(C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[sealed](../windows/sealed-cpp-component-extensions.md), [abstract](../windows/abstract-cpp-component-extensions.md), and [override](../windows/override-cpp-component-extensions.md) are available in compilations that do not use **\/ZW** or [\/clr](../build/reference/clr-common-language-runtime-compilation.md).  
  
> [!NOTE]
>  The ISO C\+\+11 Standard language has the [override](../cpp/override-specifier.md) identifier and the [final](../cpp/final-specifier.md) identifier, and both are supported in Visual Studio  Use `final` instead of `sealed` in code that is meant to be compiled as native\-only.  
  
## 예제  
  
### 설명  
 The following example shows that `sealed` is valid in native compilations.  
  
### 코드  
  
```  
// sealed_native_keyword.cpp  
#include <stdio.h>  
__interface I1 {  
   virtual void f();  
   virtual void g();  
};  
  
class X : public I1 {  
public:  
   virtual void g() sealed {}  
};  
  
class Y : public X {  
public:  
  
   // the following override generates a compiler error  
   virtual void g() {}   // C3248 X::g is sealed!  
};  
```  
  
## 예제  
  
### 설명  
 The next example shows that `override` is valid in native compilations.  
  
### 코드  
  
```  
// override_native_keyword.cpp  
#include <stdio.h>  
__interface I1 {  
   virtual void f();  
};  
  
class X : public I1 {  
public:  
   virtual void f() override {}   // OK  
   virtual void g() override {}   // C3668 I1::g does not exist  
};  
```  
  
## 예제  
  
### 설명  
 This example shows that `abstract` is valid in native compilations.  
  
### 코드  
  
```  
// abstract_native_keyword.cpp  
class X abstract {};  
  
int main() {  
   X * MyX = new X;   // C3622 cannot instantiate abstract class  
}  
```  
  
## 참고 항목  
 [Override 지정자](../windows/override-specifiers-cpp-component-extensions.md)