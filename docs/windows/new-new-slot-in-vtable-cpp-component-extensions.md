---
title: "new (new slot in vtable)  (C++ Component Extensions) | Microsoft Docs"
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
  - "new keyword [C++]"
ms.assetid: 1a9a5704-f02f-46ae-ad65-f0f2b6dbabc3
caps.latest.revision: 20
caps.handback.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# new (new slot in vtable)  (C++ Component Extensions)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`new` 키워드는 vtable에서 새 슬롯을 얻을 수 있는 가상 멤버를 가리킵니다.  
  
> [!NOTE]
>  `new` 키워드는 자주 의미를 지니고 사용됩니다.  자세한 내용은 [new](../misc/new.md)명확화 항목을 참조하세요.  
  
## 모든 런타임  
 \(모든 런타임에 적용되는 이 언어 기능에 대한 설명이 없습니다.\)  
  
## Windows 런타임\(Windows Runtime\)  
 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]에서는 지원되지 않습니다.  
  
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
 **설명**  
  
 **\/clr** 컴파일에서, `new` 는 vtable에서 새 슬롯을 얻을 수 있는 가상 멤버를 가리킵니다; 함수는 기본 클래스 메서드를 재정의 하지 않습니다.  
  
 `new`는 함수의 IL에 추가 될 새 슬롯 한정자를 사용합니다.  새 슬롯에 대한 자세한 내용은 다음을 참조하십시오:  
  
-   [\<caps:sentence id\="tgt11" sentenceid\="e9bb59a12f97840a5c3173bb77c6b5b1" class\="tgtSentence"\>MethodInfo.GetBaseDefinition 메서드\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.reflection.methodinfo.getbasedefinition.aspx)  
  
-   [\<caps:sentence id\="tgt12" sentenceid\="f6ceddd85a425f38e7ed06e94a9808a9" class\="tgtSentence"\>MethodAttributes 열거형\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.reflection.methodattributes.aspx)  
  
### 요구 사항  
 컴파일러 옵션: **\/clr**  
  
### 예제  
 **예제**  
  
 다음 샘플에서는 `new`의 효과를 보여 줍니다.  
  
```  
// newslot.cpp  
// compile with: /clr  
ref class C {  
public:  
   virtual void f() {  
      System::Console::WriteLine("C::f() called");  
   }  
  
   virtual void g() {  
      System::Console::WriteLine("C::g() called");  
   }  
};  
  
ref class D : public C {  
public:  
   virtual void f() new {  
      System::Console::WriteLine("D::f() called");  
   }  
  
   virtual void g() override {  
      System::Console::WriteLine("D::g() called");  
   }  
};  
  
ref class E : public D {  
public:  
   virtual void f() override {  
      System::Console::WriteLine("E::f() called");  
   }  
};  
  
int main() {  
   D^ d = gcnew D;  
   C^ c = gcnew D;  
  
   c->f();   // calls C::f  
   d->f();   // calls D::f  
  
   c->g();   // calls D::g  
   d->g();   // calls D::g  
  
   D ^ e = gcnew E;  
   e->f();   // calls E::f  
}  
```  
  
 **Output**  
  
  **C::f\(\) 호출**  
 **D::f\(\) 호출**  
 **D::g\(\) 호출**  
 **D::g\(\) 호출**  
 **E::f\(\) 호출**   
## 참고 항목  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)   
 [Override 지정자](../windows/override-specifiers-cpp-component-extensions.md)