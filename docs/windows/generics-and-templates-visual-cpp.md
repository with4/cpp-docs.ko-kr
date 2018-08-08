---
title: 제네릭 및 템플릿 (Visual c + +) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- generics [C++], vs. templates
- templates, C++
ms.assetid: 63adec79-b1dc-4a1a-a21d-b8a72a8fce31
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3ebb476b0a8c384759c9d44101e7bac7083103b2
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/06/2018
ms.locfileid: "39570768"
---
# <a name="generics-and-templates-visual-c"></a>제네릭 및 템플릿(Visual C++)
제네릭 및 템플릿 매개 변수가 있는 형식에 대 한 지원을 제공 하는 두 언어 기능 됩니다. 그러나 다른 되며 다른 용도로 사용 됩니다. 이 항목에서는 여러 차이점이 개요를 제공합니다.  
  
 자세한 내용은 [Windows 런타임 및 관리 되는 템플릿](../windows/windows-runtime-and-managed-templates-cpp-component-extensions.md)합니다.  
  
## <a name="comparing-templates-and-generics"></a>템플릿과 제네릭 비교  
 제네릭 및 c + + 템플릿 간의 주요 차이점:  
  
-   제네릭 됩니다 제네릭 형식이 런타임 시에 대체 됩니다. 런타임 시 아직 매개 변수화 된 형식의 되지 않으므로 컴파일 타임에 템플릿 특수화 된  
  
-   특히 공용 언어 런타임에서 MSIL의 제네릭을 지원합니다. 런타임에서 제네릭에 대 한 알 수, 때문에 제네릭 형식을 포함 하는 어셈블리를 참조할 때 제네릭 형식에 대 한 특정 형식은 대체할 수 있습니다. 템플릿 반면 해결 일반 형식으로 컴파일할 때 하 고 결과 형식을 다른 어셈블리의 특수화 될 수 없습니다.  
  
-   두 명의 다른 어셈블리에서 특수화 된 제네릭 형식이 같은 인수는 같은 형식입니다. 템플릿 인수는 런타임에서 다른 형식일 것으로 간주 됩니다 동일한 형식 사용 하 여 두 명의 다른 어셈블리의 특수화입니다.  
  
-   제네릭 (이 아닙니다 값 유형 마다 고유한 구현을 포함 하는 값 형식의 경우 true) 모든 참조 형식 인수에 사용 되는 실행 코드의 한 부분으로 생성 됩니다. JIT 컴파일러에는 제네릭 인식 되며 형식 인수로 사용 되는 참조 또는 값 형식에 대 한 코드를 최적화할 수 있습니다. 템플릿은 각 특수화에 대 한 별도 런타임 코드를 생성합니다.  
  
-   제네릭 없도록 비형식 템플릿 매개 변수를 같은 `template <int i> C {}`합니다. 템플릿을 사용 합니다.  
  
-   제네릭을 명시적 특수화 (즉, 특정 형식에 대 한 템플릿 사용자 지정 구현)를 허용 하지 않습니다. 템플릿 수행 합니다.  
  
-   제네릭 (하위 집합에 대 한 형식 인수의 사용자 지정 구현을) 부분 특수화를 허용 하지 않습니다. 템플릿 수행 합니다.  
  
-   제네릭 형식 매개 변수는 제네릭 형식에 대 한 기본 클래스로 사용할 수 없습니다. 템플릿 수행 합니다.  
  
-   템플릿 템플릿 템플릿 매개 변수를 지원 합니다. (예: `template<template<class T> class X> class MyClass`), 제네릭 되지 않지만 합니다.  
  
## <a name="combining-templates-and-generics"></a>템플릿과 Generic 결합  
  
-   제네릭의 기본적인 차이점은 템플릿과 제네릭 결합 하는 응용 프로그램을 구축 하는 것에 대 한 영향을 줍니다. 예를 들어, 해당 템플릿을 다른 언어를 제네릭으로 노출에 대 한 제네릭 래퍼를 만들려면 원하는 템플릿 클래스가 있다고 가정 합니다. 제네릭 사용 템플릿은 컴파일 시간에 해당 형식 매개 변수에 있는 해야 하므로 다음 템플릿에 있지만 전달 하는 형식 매개 변수에 사용할 수 없습니다 있지만 제네릭 형식 매개 변수를 런타임 시까지 해결 하지 못합니다. 중첩 제네릭 내에서 템플릿을 없으므로 작동 하지 않습니다 하거나 템플릿을 런타임에 인스턴스화할 수 있는 임의의 제네릭 형식에 대 한 컴파일 시간에 확장 방법이 있습니다.  
  
## <a name="example"></a>예  
  
### <a name="description"></a>설명  
 다음 예제에서는 템플릿과 제네릭을 함께 사용 하는 간단한 예를 보여 줍니다. 이 예제에서는 템플릿 클래스는 제네릭 형식으로을 통해 해당 매개 변수를 전달합니다. 반대로 불가능합니다.  
  
 Visual c + + 어셈블리를 로컬 템플릿 코드를 사용 하 여 기존 제네릭 API에서 빌드 하려는 경우 또는 없습니다 supporte 템플릿의 특정 기능을 활용 하려면 제네릭 형식으로 매개 변수화의 추가 계층을 추가 해야 할 때이 관용구를 사용할 수 있습니다. 제네릭 d입니다.  
  
### <a name="code"></a>코드  
  
```cpp  
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
  
```Output  
F  
```  
  
## <a name="see-also"></a>참고 항목  
 [제네릭](../windows/generics-cpp-component-extensions.md)