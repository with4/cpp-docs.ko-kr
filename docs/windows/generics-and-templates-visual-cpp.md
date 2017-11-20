---
title: "템플릿 (Visual c + +) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- generics [C++], vs. templates
- templates, C++
ms.assetid: 63adec79-b1dc-4a1a-a21d-b8a72a8fce31
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0ea175a0f71c412583065eb2df4e04928ffe57ae
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="generics-and-templates-visual-c"></a>제네릭 및 템플릿(Visual C++)
제네릭과 템플릿의 지 매개 변수가 있는 형식에 대 한 지원을 제공 하는 두 언어 기능. 그러나 다른 되며 다른 용도로 사용 합니다. 이 항목에서는 많은 차이점에 대 한 개요를 제공 합니다.  
  
 자세한 내용은 참조 [Windows 런타임 및 관리 되는 템플릿](../windows/windows-runtime-and-managed-templates-cpp-component-extensions.md)합니다.  
  
## <a name="comparing-templates-and-generics"></a>템플릿과 제네릭 비교  
 C + + 템플릿 간의 주요 차이점:  
  
-   제네릭은 형식을 대신 사용 됩니다 하 런타임에 제네릭 됩니다. 런타임에 여전히 매개 변수가 있는 형식이 되기 때문에 컴파일 타임에 템플릿 특수화 된  
  
-   공용 언어 런타임에서 특히 msil에서 제네릭을 지원합니다. 런타임에서 제네릭에 대 한 때문에 제네릭 형식을 포함 하는 어셈블리를 참조할 때 제네릭 형식에 대 한 특정 유형은 대체할 수 있습니다. 템플릿, 반면, 해결 일반 형식으로 컴파일 타임에 하 고 결과 형식에서 다른 어셈블리의에서 특수화 될 수 있습니다.  
  
-   두 명의 다른 어셈블리 특수 제네릭 형식이 같은 인수는 같은 형식입니다. 템플릿은 특수화 두 명의 다른 어셈블리와 동일한 형식 인수는 런타임에서 서로 다른 형식으로 간주 됩니다.  
  
-   제네릭 (사실이 아닙니다 값 유형 마다 고유한 구현 하는 값 형식)는 모든 참조 형식 인수에 사용 되는 실행 코드의 한 부분으로 생성 됩니다. JIT 컴파일러가 제네릭에 대 한 알고 있고 형식 인수로 사용 되는 참조 또는 값 형식에 대 한 코드를 최적화 수입니다. 템플릿은 각 특수화에 대 한 별도 런타임 코드를 생성합니다.  
  
-   제네릭 비형식 템플릿 매개 변수를 같은 허용 하지 않습니다 `template <int i> C {}`합니다. 템플릿 수 있습니다.  
  
-   제네릭을 명시적 특수화 (즉, 특정 형식에 대 한 템플릿 사용자 지정 구현)를 허용 하지 않습니다. 서식 파일을 수행합니다.  
  
-   제네릭 부분 특수화 (하위 집합에 대 한 형식 인수 중 사용자 지정 구현)를 허용 하지 않습니다. 서식 파일을 수행합니다.  
  
-   제네릭 형식 매개 변수는 제네릭 형식에 대 한 기본 클래스로 사용할 수 없습니다. 서식 파일을 수행합니다.  
  
-   템플릿 템플릿 템플릿 매개 변수를 지원 (예: `template<template<class T> class X> class MyClass`)을 포함 하지만 제네릭 하지 않습니다.  
  
## <a name="combining-templates-and-generics"></a>템플릿과 제네릭 결합  
  
-   제네릭의 기본적인 차이점은 템플릿과 제네릭 결합 하는 응용 프로그램을 빌드하기 위한 영향을 줍니다. 예를 들어 제네릭으로 다른 언어에 해당 서식 파일을 노출 하는 일반 래퍼에 대 한 만들려고 한다고 하는 템플릿 클래스를 있다고 가정 합니다. 제네릭 take 템플릿을 컴파일 타임에 해당 형식 매개 변수가 해야 하므로 다음 하도록 서식 파일을 전달 하는 형식 매개 변수 없지만 런타임이 될 때까지 제네릭 형식 매개 변수를 해결 하지 않습니다. 제네릭 안의 템플릿에 중첩 하거나 수 없으므로 작동 하지 템플릿을 런타임에 인스턴스화할 수 있는 임의의 제네릭 형식에 대 한 컴파일 타임에 확장 방식은 없습니다.  
  
## <a name="example"></a>예제  
  
### <a name="description"></a>설명  
 다음 예제에서는 템플릿과 제네릭을 함께 사용 하 여의 간단한 예를 보여 줍니다. 이 예제에서는 템플릿 클래스는 제네릭 형식에을 통해 해당 매개 변수를 전달합니다. 반대로 수는 없습니다.  
  
 Visual c + + 어셈블리에 로컬인 템플릿 코드와 함께 기존 제네릭 API에 빌드 하려는 경우 또는 하지 supporte 서식 파일의 특정 기능을 활용 하는 제네릭 형식에 매개 변수화의 추가 계층을 추가 해야 할 때이 관용구를 사용할 수 있습니다. 제네릭 하 여 d입니다.  
  
### <a name="code"></a>코드  
  
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
  
### <a name="output"></a>출력  
  
```  
F  
```  
  
## <a name="see-also"></a>참고 항목  
 [제네릭](../windows/generics-cpp-component-extensions.md)