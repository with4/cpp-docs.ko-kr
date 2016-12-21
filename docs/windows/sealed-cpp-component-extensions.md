---
title: "sealed  (C++ Component Extensions) | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "sealed_cpp"
  - "sealed"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "sealed keyword [C++]"
ms.assetid: 3d0d688a-41aa-45f5-a25a-65c44206521e
caps.latest.revision: 26
caps.handback.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# sealed  (C++ Component Extensions)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`sealed`는 가상 멤버를 재정의할 수 없거나 형식을 기본 형식으로 사용할 수 없음을 나타내는 ref 클래스에 대한 상황에 맞는 키워드입니다.  
  
> [!NOTE]
>  ISO C\+\+11 표준 언어에는 Visual Studio에서 지원되는 [final](../cpp/final-specifier.md) 키워드가 있습니다.  표준 클래스에서는 `final`을 사용하고 ref 클래스에서는 `sealed`를 사용합니다.  
  
## 모든 런타임  
 **구문**  
  
```  
  
ref class identifier sealed {...};  
virtual return-type identifier() sealed {...};  
  
```  
  
 **매개 변수**  
  
 *identifier*  
 함수나 클래스의 이름입니다.  
  
 *return\-type*  
 함수에서 반환하는 형식입니다.  
  
 **설명**  
  
 첫 번째 구문 예에서는 클래스가 봉인되어 있고,  두 번째 예에서는 가상 함수가 봉인되어 있습니다.  
  
 `sealed` 키워드는 네이티브 대상에 유효하며 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] 및 CLR\(공용 언어 런타임\)에도 유효합니다.  자세한 내용은 [재정의 지정자 및 네이티브 컴파일](../dotnet/how-to-declare-override-specifiers-in-native-compilations-cpp-cli.md)을 참조하세요.  
  
 `__is_sealed (` `type` `)` 형식 특성을 사용하여 형식이 봉인되어 있는지 여부를 컴파일 시간에 감지할 수 있습니다.  자세한 내용은 [Compiler Support for Type Traits](../windows/compiler-support-for-type-traits-cpp-component-extensions.md)을 참조하세요.  
  
 `sealed`는 상황에 맞는 키워드입니다.  자세한 내용은 [상황에 맞는 키워드](../windows/context-sensitive-keywords-cpp-component-extensions.md)를 참조하세요.  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
 [Ref 클래스 및 구조체](http://msdn.microsoft.com/library/windows/apps/hh699870.aspx)를 참조하세요.  
  
### 요구 사항  
 컴파일러 옵션: **\/ZW**  
  
## 공용 언어 런타임  
 \(이 언어 기능에는 공용 언어 런타임에만 적용되는 설명이 없습니다.\)  
  
### 요구 사항  
 컴파일러 옵션: **\/clr**  
  
### 예제  
 다음 코드 예제에서는 가상 멤버에 대한 `sealed`의 영향을 보여 줍니다.  
  
```cpp  
// sealed_keyword.cpp  
// compile with: /clr  
interface struct I1 {  
   virtual void f();  
   virtual void g();  
};  
  
ref class X : I1 {  
public:  
   virtual void f() {  
      System::Console::WriteLine("X::f override of I1::f");  
   }  
  
   virtual void g() sealed {  
      System::Console::WriteLine("X::f override of I1::g");  
   }  
};  
  
ref class Y : public X {  
public:  
   virtual void f() override {  
      System::Console::WriteLine("Y::f override of I1::f");  
   }  
  
   /*  
   // the following override generates a compiler error  
   virtual void g() override {  
      System::Console::WriteLine("Y::g override of I1::g");  
   }    
   */  
};  
  
int main() {  
   I1 ^ MyI = gcnew X;  
   MyI -> f();  
   MyI -> g();  
  
   I1 ^ MyI2 = gcnew Y;  
   MyI2 -> f();  
}  
```  
  
 **출력**  
  
  **X::f override of I1::f**  
 **X::f override of I1::g**  
 **Y::f override of I1::f** 다음 코드 예제에서는 클래스를 sealed로 표시하는 방법을 보여 줍니다.  
  
```cpp  
// sealed_keyword_2.cpp  
// compile with: /clr  
interface struct I1 {  
   virtual void f();  
};  
  
ref class X sealed : I1 {  
public:  
   virtual void f() override {}  
};  
  
ref class Y : public X {   // C3246 base class X is sealed  
public:  
   virtual void f() override {}  
};  
```  
  
## 참고 항목  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)