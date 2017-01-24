---
title: "Explicit Overrides  (C++ Component Extensions) | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "overriding, override [C++]"
ms.assetid: 4ec3eaf5-163b-4df8-8f16-7a2ec04c3d0f
caps.latest.revision: 21
caps.handback.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Explicit Overrides  (C++ Component Extensions)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 항목에 명시적으로 기본 클래스 또는 인터페이스의 멤버를 재정의 하는 방법을 설명합니다.  명명된 된 \(명시적\) 재정의는 이름이 다른 파생 메서드로 메서드를 재정의하기 위해 사용해야 합니다.  
  
## 모든 런타임  
 **구문**  
  
```  
  
        overriding-function-declarator = type::function [,type::function] { overriding-function-definition }  
overriding-function-declarator = function { overriding-function-definition }  
```  
  
 **매개 변수**  
  
 *overriding\-function\-declarator*  
 재정의 함수의 반환 형식, 이름 및 인수 목록입니다.  재정의 함수는 재정의 된 함수와 같은 이름을 가지고 있지 않은 점을 참고하십시오.  
  
 *type*  
 재정의하는 함수를 포함하는 기본 형식입니다.  
  
 *function*  
 재정의를 하기 위한 하나 이상의 함수이름을 쉼표로 구분한 목록입니다.  
  
 *overriding\-function\-definition*  
 재정의 함수를 정의하는 함수 본문입니다.  
  
 **설명**  
  
 명시적 재정의를 사용하여 메서드 시그니처에 대한 별칭을 만들거나 같은 시그니처 메서드에 대한 다른 구현을 제공합니다.  
  
 상속된 형식 및 상속된 형식 멤버의 동작을 수정하는 방법에 대한 내용은 [Override 지정자](../windows/override-specifiers-cpp-component-extensions.md)을 참고하십시오.  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
  
### 요구 사항  
 컴파일러 옵션: **\/ZW**  
  
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
 **설명**  
  
 **\/clr:oldSyntax** 로 컴파일된 코드 또는 네이티브 코드의 명시적 재정의에 대한 자세한 정보는 [명시적 재정의](../cpp/explicit-overrides-cpp.md)에서 확인하십시오.  
  
### 요구 사항  
 컴파일러 옵션: **\/clr**  
  
### 예제  
 **예제**  
  
 다음 코드 예제에서는 단순하고 암시적인 재정의와 재정의를 사용하지 않고 기본 인터페이스의 멤버를 구현하는 방법을 보여줍니다.  
  
```  
// explicit_override_1.cpp  
// compile with: /clr  
interface struct I1 {  
   virtual void f();  
};  
  
ref class X : public I1 {  
public:  
   virtual void f() {  
      System::Console::WriteLine("X::f override of I1::f");  
   }  
};  
  
int main() {  
   I1 ^ MyI = gcnew X;  
   MyI -> f();  
}  
```  
  
 **Output**  
  
  **I1::f의 X::f 재정의** **예제**  
  
 다음 코드 예제에서는 명시적 재정의 구문을 사용하여 공용 시그니처의 모든 인터페이스 멤버를 구현하는 방법을 보여줍니다.  
  
```  
  
// explicit_override_2.cpp  
// compile with: /clr  
interface struct I1 {  
   virtual void f();  
};  
  
interface struct I2 {  
   virtual void f();  
};  
  
ref struct X : public I1, I2 {  
   virtual void f() = I1::f, I2::f {  
      System::Console::WriteLine("X::f override of I1::f and I2::f");  
   }  
};  
  
int main() {  
   I1 ^ MyI = gcnew X;  
   I2 ^ MyI2 = gcnew X;  
   MyI -> f();  
   MyI2 -> f();  
}  
```  
  
 **Output**  
  
  **X::f 재정의 I1::f 와 I2::f**  
 **X::f 재정의 I1::f 와 I2::f** **예제**  
  
 다음 코드 예제에서는 함수 재정의가 구현 하는 함수로부터 다른 이름을 가질 수 있는 방법에 대해 보여줍니다.  
  
```  
// explicit_override_3.cpp  
// compile with: /clr  
interface struct I1 {  
   virtual void f();  
};  
  
ref class X : public I1 {  
public:  
   virtual void g() = I1::f {  
      System::Console::WriteLine("X::g");  
   }  
};  
  
int main() {  
   I1 ^ a = gcnew X;  
   a->f();  
}  
```  
  
 **Output**  
  
  **X::g** **예제**  
  
 다음 코드 예제에서는 형식 안전 컬렉션을 구현 하는 명시적 인터페이스 구현을 보여줍니다.  
  
```  
// explicit_override_4.cpp  
// compile with: /clr /LD  
using namespace System;  
ref class R : ICloneable {  
   int X;  
  
   virtual Object^ C() sealed = ICloneable::Clone {  
      return this->Clone();  
   }  
  
public:  
   R() : X(0) {}  
   R(int x) : X(x) {}  
  
   virtual R^ Clone() {  
      R^ r = gcnew R;  
      r->X = this->X;  
      return r;  
   }  
};  
```  
  
## 참고 항목  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)