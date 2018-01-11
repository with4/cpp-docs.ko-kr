---
title: "abstract (c + + 구성 요소 확장명) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- abstract
- abstract_cpp
dev_langs: C++
helpviewer_keywords: abstract keyword [C++]
ms.assetid: cbae3408-0378-4ac8-b70d-c016b381a6d5
caps.latest.revision: "21"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7b935aabeb048d955941a41f6a50735897a53009
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="abstract--c-component-extensions"></a>abstract(C++ 구성 요소 확장)
`abstract` 키워드는 다음의 하나를 선언합니다.  
  
-   형식은 기본 형식으로 사용될 수 있지만 형식 자체는 인스턴스화될 수 없습니다.  
  
-   형식 멤버 함수는 파생된 형식에서만 정의될 수 있습니다.  
  
## <a name="all-platforms"></a>모든 플랫폼  
 **구문**  
  
```  
  
      class-declaration  
      class-identifier  
      abstract {}  
virtualreturn-typemember-function-identifier() abstract ;  
  
```  
  
 **주의**  
  
 첫 번째 예제 구문에서는 클래스를 추상으로 선언합니다. *클래스 선언* 구성 요소는 네이티브 c + + 선언 될 수 있습니다 (`class` 또는 `struct`), 또는 c + + 확장 선언 (`ref class` 또는 `ref struct`) 하는 경우는 **/ZW** 또는 **/clr** 컴파일러 옵션을 지정 합니다.  
  
 두 번째 예제 구문에서는 가상 멤버 함수를 추상으로 선언합니다. 함수를 추상으로 선언하는 것은 함수를 순수 가상 함수로 선언하는 것과 같습니다. 멤버 함수를 추상으로 선언하면 바깥쪽 클래스가 추상으로 선언됩니다.  
  
 `abstract` 키워드는 네이티브 및 플랫폼별 코드에서 지원 됩니다; 즉, 컴파일할 수 여부에 관계 없이 **/ZW** 또는 **/clr** 컴파일러 옵션입니다.  
  
 형식을 추상으로 경우 컴파일 타임에 감지할 수는 `__is_abstract(type)` 형식 특성입니다. 자세한 내용은 참조 [형식 특성에 대 한 컴파일러 지원](../windows/compiler-support-for-type-traits-cpp-component-extensions.md)합니다.  
  
 `abstract` 키워드는 상황에 맞는 재정의 지정자입니다. 상황에 맞는 키워드에 대 한 자세한 내용은 참조 [상황에 맞는 키워드](../windows/context-sensitive-keywords-cpp-component-extensions.md)합니다. 재정의 지정자에 대 한 자세한 내용은 참조 [하는 방법: 네이티브 컴파일에 Override 지정자 선언](../dotnet/how-to-declare-override-specifiers-in-native-compilations-cpp-cli.md)합니다.  
  
## <a name="windows-runtime"></a>Windows 런타임  
 자세한 내용은 참조 [Ref 클래스 및 구조체](http://msdn.microsoft.com/library/windows/apps/hh699870.aspx)합니다.  
  
### <a name="requirements"></a>요구 사항  
 컴파일러 옵션: **/ZW**  
  
## <a name="common-language-runtime"></a>공용 언어 런타임 
  
### <a name="requirements"></a>요구 사항  
 컴파일러 옵션: **/clr**  
  
### <a name="examples"></a>예제  
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
  
 다음 코드 예제에서는 `abstract`로 표시된 네이티브 클래스를 인스턴스화하기 때문에 오류가 발생하는 경우를 보여 줍니다. 이 오류는 여부에 관계 없이 발생는 **/clr** 컴파일러 옵션입니다.  
  
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
  
 다음 예제에서는 `f` 함수가 정의를 포함하지만 `abstract`로 표시되기 때문에 오류가 발생하는 경우를 보여 줍니다. 예제의 마지막 문에서는 추상 가상 함수를 선언하는 것이 순수 가상 함수를 선언하는 것과 일치함을 보여 줍니다.  
  
```  
// abstract_keyword_3.cpp  
// compile with: /clr  
ref class X {  
public:  
   virtual void f() abstract {}   // C3634  
   virtual void g() = 0 {}   // C3634  
};  
```  
  
## <a name="see-also"></a>참고 항목  
 [런타임 플랫폼용 구성 요소 확장](../windows/component-extensions-for-runtime-platforms.md)