---
title: "Generics and Templates (Visual C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
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
  - "generics [C++], vs. templates"
  - "templates, C++"
ms.assetid: 63adec79-b1dc-4a1a-a21d-b8a72a8fce31
caps.latest.revision: 19
caps.handback.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Generics and Templates (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

제네릭과 템플릿은 모두 매개 변수가 있는 형식을 지원하는 언어 기능입니다.  그러나 다양하고 여러 용도를 가집니다.  이 항목에서는 이 다양성에 대해 간략하게 설명합니다.  
  
 자세한 내용은 [Windows Runtime and Managed Templates](../windows/windows-runtime-and-managed-templates-cpp-component-extensions.md) 및 [템플릿 개요](../Topic/Templates%20Overview.md)를 참조하십시오.  
  
## 제네릭과 템플릿 비교  
 C\+\+ 템플릿과 제네릭의 중요한 차이점:  
  
-   제네릭은 런타임에 형식으로 대체될 때까지 제네릭됩니다.  템플릿은 컴파일 타임에 특수화 됩니다. 그래서 런타임엔 여전히 매개 변수가 있는 형식이 아니게 됩니다.  
  
-   특히 공용 언어 런타임에서 MSIL에서 제네릭을 지원합니다.  런타임에서 제네릭 정보 때문에 제네릭 형식이 포함된 어셈블리를 참조 하는 경우 제네릭 형식에 대한 특정 형식은 대체할 수 있습니다.  템플릿, 반대로 해결 일반적인 형식으로 컴파일 타임에 한 다른 어셈블리에 있는 결과 형식을 특수화할 수 있습니다.  
  
-   두 명의 서로 다른 어셈블리에 특수화 된 제네릭 형식이 같은 인수는 같은 형식입니다.  인수 형식으로 간주 런타임에서 형식이 같은 두 명의 서로 다른 어셈블리에 특수화 된 템플릿이 있습니다.  
  
-   제네릭 \(값 유형 마다 구현 하는 고유한 값, 형식에 적용 되지 않음\)은 모든 참조 형식 인수에 사용되는 실행 코드의 한 부분으로 생성됩니다.  JIT 컴파일러 제네릭에 대한 정보 및 형식 인수로 사용되는 참조 또는 값 형식에 대한 코드를 최적화할 수 있습니다.  템플릿은 각 특수화에 대한 별도의 런타임 코드를 생성합니다.  
  
-   제네릭은 `template <int i> C {}` 같은 비형식 템플릿 매개 변수를 허용하지 않습니다.  템플릿은 그것들을 허용합니다.  
  
-   제네릭에서는 명시적 특수화를 허용하지 않습니다. \(즉, 특정 형식에 대한 템플릿을 사용자 지정하여 구현할 수 없습니다\)  템플릿 또한 그렇습니다.  
  
-   제네릭에서는 부분 특수화를 허용하지 않습니다. \(즉, 형식 인수의 하위 집합을 사용자 지정하여 구현할 수 없습니다\)  템플릿 또한 그렇습니다.  
  
-   제네릭에서는 형식 매개 변수를 제네릭 형식에 대한 기본 클래스로 사용할 수 없습니다.  템플릿 또한 그렇습니다.  
  
-   서식 파일은 템플릿\-템플릿 매개 변수를 지원합니다. \(예,  `template<template<class T> class X> class MyClass`\), 그러나 제네릭은 지원하지 않습니다.  
  
## 제네릭과 템플릿의 결합  
  
-   제네릭의 기본적인 차이점은 템플릿과 제네릭 결합하는 응용 프로그램을 구축하는 것입니다.  예를 들어, 제네릭으로 해당 서식 파일을 다른 언어에 노출하게 만드는 제네릭 래퍼를 만들 수 있는 템플릿 클래스를 가지고 있습니다.  제네릭 템플릿은 컴파일 타임에 해당 형식 매개 변수를 가질 필요가 있기 때문에 그 다음, 템플릿에 불구하고 전달하는 형식 매개 변수를 가질 수 있지만, 제네릭은 런타임까지 형식 매개 변수가 해결되지 않습니다.  런타임에 인스턴스화 할 수 모든 제네릭 형식의 경우 컴파일 타임에 템플릿을 확장하는 방법이 없기 때문에 제네릭 내부 템플릿을 중첩하는 것 중 하나가 작동하지 않습니다.  
  
## 예제  
  
### 설명  
 다음 예제에서는 템플릿과 제네릭 함께 사용하는 간단한 예제를 보여줍니다.  이 예제에서는 템플릿 클래스가 매개 변수를 제네릭 형식으로 통해 전달합니다.  반대는 불가능합니다.  
  
 이 방법은 Visual C\+\+ 어셈블리를 로컬 템플릿 코드를 사용하여 기존 일반 API를 빌드 하려는 경우 또는 템플릿에서 제네릭을 지원하지 않는 특정 기능을 사용하는 제네릭 형식에는 추가적인 매개 변수화를 추가해야 할 때 사용할 수 있습니다.  
  
### 코드  
  
```  
// templates_and_generics.cpp  
// compile with: /clr  
using namespace System;  
  
generic <class ItemType>  
ref class MyGeneric {  
   ItemType m_item;  
  
public:  
   MyGeneric(ItemType item) : m_item(item) {}  
   void F() {   
      Console::WriteLine("F");   
   }  
};  
  
template <class T>  
public ref class MyRef {  
MyGeneric<T>^ ig;  
  
public:  
   MyRef(T t) {  
      ig = gcnew MyGeneric<T>(t);  
      ig->F();  
    }      
};  
  
int main() {  
   // instantiate the template  
   MyRef<int>^ mref = gcnew MyRef<int>(11);  
}  
```  
  
### Output  
  
```  
F  
```  
  
## 참고 항목  
 [Generics](../windows/generics-cpp-component-extensions.md)