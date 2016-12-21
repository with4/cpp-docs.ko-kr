---
title: "abstract  (C++ Component Extensions) | Microsoft Docs"
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
  - "abstract"
  - "abstract_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "abstract keyword [C++]"
ms.assetid: cbae3408-0378-4ac8-b70d-c016b381a6d5
caps.latest.revision: 21
caps.handback.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# abstract  (C++ Component Extensions)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`abstract` 키워드는 다음의 하나를 선언합니다.  
  
-   형식은 기본 형식으로 사용될 수 있지만 형식 자체는 인스턴스화될 수 없습니다.  
  
-   형식 멤버 함수는 파생된 형식에서만 정의될 수 있습니다.  
  
## 모든 플랫폼  
 **구문**  
  
```  
  
class-declaration class-identifier abstract {}  
virtual return-type member-function-identifier() abstract ;  
  
```  
  
 **설명**  
  
 첫 번째 예제 구문에서는 클래스를 추상으로 선언합니다.  *class\-declaration* 구성 요소는 네이티브 C\+\+ 선언\(`class` 또는 `struct`\)이거나, **\/ZW** 또는 **\/clr** 컴파일러 옵션이 지정된 경우에는 C\+\+ 확장 선언\(`ref class` 또는 `ref struct`\)일 수 있습니다.  
  
 두 번째 예제 구문에서는 가상 멤버 함수를 추상으로 선언합니다.  함수를 추상으로 선언하는 것은 함수를 순수 가상 함수로 선언하는 것과 같습니다.  멤버 함수를 추상으로 선언하면 바깥쪽 클래스가 추상으로 선언됩니다.  
  
 `abstract` 키워드는 네이티브 및 플랫폼별 코드에서 지원됩니다. 즉, **\/ZW** 또는 **\/clr** 컴파일러 옵션을 사용하거나 사용하지 않고 컴파일할 수 있습니다.  
  
 컴파일 시간에 `__is_abstract(``type``)` 형식 특성을 사용하여 형식이 추상인지를 검색할 수 있습니다.  자세한 내용은 [Compiler Support for Type Traits](../windows/compiler-support-for-type-traits-cpp-component-extensions.md)을 참조하세요.  
  
 `abstract` 키워드는 상황에 맞는 재정의 지정자입니다.  상황에 맞는 키워드에 대한 자세한 내용은 [상황에 맞는 키워드](../windows/context-sensitive-keywords-cpp-component-extensions.md)를 참조하세요.  재정의 지정자에 대한 자세한 내용은 [방법: 네이티브 컴파일에 재정의 지정자 선언](../dotnet/how-to-declare-override-specifiers-in-native-compilations-cpp-cli.md)을 참조하세요.  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
 자세한 내용은 [Ref 클래스 및 구조체](http://msdn.microsoft.com/library/windows/apps/hh699870.aspx)를 참조하세요.  
  
### 요구 사항  
 컴파일러 옵션: **\/ZW**  
  
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
  
### 요구 사항  
 컴파일러 옵션: **\/clr**  
  
### 예  
 **예제**  
  
 다음 코드 예제에서는 `X` 클래스가 `abstract`로 표시되기 때문에 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// abstract_keyword.cpp  
// compile with: /clr  
ref class X abstract {  
public:  
   virtual void f() {}  
};  
  
int main() {  
   X ^ MyX = gcnew X;   // C3622  
}  
```  
  
 **예제**  
  
 다음 코드 예제에서는 `abstract`로 표시된 네이티브 클래스를 인스턴스화하기 때문에 오류가 발생하는 경우를 보여 줍니다.  이 오류는 **\/clr** 컴파일러 옵션 사용 여부와 관계없이 발생합니다.  
  
```  
// abstract_keyword_2.cpp  
class X abstract {  
public:  
   virtual void f() {}  
};  
  
int main() {  
   X * MyX = new X; // C3622: 'X': a class declared as 'abstract'  
                    // cannot be instantiated. See declaration of 'X'}  
  
```  
  
 **예제**  
  
 다음 예제에서는 `f` 함수가 정의를 포함하지만 `abstract`로 표시되기 때문에 오류가 발생하는 경우를 보여 줍니다.  예제의 마지막 문에서는 추상 가상 함수를 선언하는 것이 순수 가상 함수를 선언하는 것과 일치함을 보여 줍니다.  
  
```  
// abstract_keyword_3.cpp  
// compile with: /clr  
ref class X {  
public:  
   virtual void f() abstract {}   // C3634  
   virtual void g() = 0 {}   // C3634  
};  
```  
  
## 참고 항목  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)