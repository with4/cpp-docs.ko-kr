---
title: "Generic Functions (C++/CLI) | Microsoft Docs"
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
  - "functions [C++], generic"
  - "generic methods"
  - "generics [C++], functions"
  - "methods [C++], generic"
  - "generic functions"
ms.assetid: 8e409364-58f9-4360-b486-e7d555e0c218
caps.latest.revision: 21
caps.handback.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Generic Functions (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

제네릭 함수는 형식 매개 변수로 선언된 함수입니다.  호출 하면 실제 형식은 형식 매개 변수 대신 사용됩니다.  
  
## 모든 플랫폼  
 **설명**  
  
 이 기능은 모든 플랫폼에 적용되지 않습니다.  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
 **설명**  
  
 이 기능은 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]에서 지원되지 않습니다.  
  
### 요구 사항  
 컴파일러 옵션: **\/ZW**  
  
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
 제네릭 함수는 형식 매개 변수로 선언된 함수입니다.  호출 하면 실제 형식은 형식 매개 변수 대신 사용됩니다.  
  
 **구문**  
  
```  
[attributes] [modifiers]  
return-type identifier <type-parameter identifier(s)>  
[type-parameter-constraints clauses]  
  
([formal-parameters])  
{  
   function-body  
}  
```  
  
 **매개 변수**  
  
 *attributes*\(옵션\)  
 추가 선언 정보입니다.  특성 및 특성 클래스에 대한 자세한 내용은 특성을 참조하십시오.  
  
 *modifiers* \(선택적 요소\)  
 Static.   `virtual`와 같은 함수 한정자는 가상 메서드를 제네릭 될 수 있으므로 허용 되지 않습니다.  
  
 *return\-type*  
 메서드에서 반환하는 형식입니다.  반환 형식이 void 인 경우 반환 값은 필요하지 않습니다.  
  
 *identifier*  
 함수 이름  
  
 *type\-parameter identifier\(s\)*  
 쉼표로 구분된 식별자 목록입니다.  
  
 *formal\-parameters*\(옵션\)  
 매개 변수 목록  
  
 *type\-parameter\-constraints\-clauses*  
 이 유형의 인수에 사용 가능한 유형에 대한 제한을 지정하고,  [Constraints on Generic Type Parameters \(C\+\+\/CLI\)](../windows/constraints-on-generic-type-parameters-cpp-cli.md)에 지정된 형태를 취합니다.  
  
 *function\-body*  
 본문 메서드 형식 매개 변수 식별자를 참조할 수도 있습니다.  
  
 **설명**  
  
 제네릭 함수는 제네릭 형식 매개 변수가 선언된 함수입니다.  클래스 또는 구조체 또는 독립 실행형 함수에서 메서드가 될 수 있습니다.  단일 제네릭 선언은 대체적으로 제네릭 형식 매개 변수에 대한 실제 다른 종류의 다른 함수를 암시적으로 선언합니다.  
  
 [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)]에서, 클래스 나 구조체 생성자는 제네릭 형식 매개 변수로 선언 할 수 없습니다.  
  
 호출될 때, 제네릭 형식 매개 변수는 실제 형식으로 대체됩니다.  템플릿 함수 호출 구문을 사용하여 꺾쇠 괄호에 실제 형식은 명시적으로 지정할 수 있습니다.  형식 매개 변수없이 호출하면 컴파일러는 함수 호출에 제공된 매개 변수의 실제 유형을 추론하려고 시도합니다.  제네릭 함수를 호출하는 경우 사용된 매개 변수에서 의도된 형식 인수를 추론할 수 없으면 컴파일러에서 오류를 보고합니다.  
  
### 요구 사항  
 컴파일러 옵션: **\/clr**  
  
### 예제  
 **예제**  
  
 다음 코드 예제에서는 제네릭 함수를 보여줍니다.  
  
```  
// generics_generic_function_1.cpp  
// compile with: /clr  
generic <typename ItemType>  
void G(int i) {}  
  
ref struct A {  
   generic <typename ItemType>  
   void G(ItemType) {}  
  
   generic <typename ItemType>  
   static void H(int i) {}  
};  
  
int main() {  
   A myObject;  
  
   // generic function call  
   myObject.G<int>(10);  
  
   // generic function call with type parameters deduced  
   myObject.G(10);  
  
   // static generic function call  
   A::H<int>(10);  
  
   // global generic function call  
   G<int>(10);  
}  
```  
  
 **예제**  
  
 서명 또는 인자, 함수에 대한 형식 매개 변수의 수에 따라 제네릭 함수를 오버 로드할 수 있습니다.  또한 일부 형식 매개 변수에서 다른 기능으로 제네릭 함수 이름이 같은 제네릭이 아닌 함수를 오버 로드할 수 있습니다.  예를 들어, 이제 다음과 같은 함수가 오버로드될 수 있습니다:  
  
```  
// generics_generic_function_2.cpp  
// compile with: /clr /c  
ref struct MyClass {  
   void MyMythod(int i) {}  
  
   generic <class T>   
   void MyMythod(int i) {}  
  
   generic <class T, class V>   
   void MyMythod(int i) {}  
};  
```  
  
 **예제**  
  
 다음 예제에서는 배열에서 첫 번째 요소를 찾기 위해 제네릭 함수를 사용합니다.  기본 클래스 `MyBaseClass` 에서 상속 되는  `MyClass` 을 선언합니다.,   `MyClass`는 기본 클래스 내에서 다른 제네릭 함수 `MyBaseClassFunction` 를 호출 하는 일반 함수가 포함됩니다.  `MyFunction` .   **main**에서, 제네릭 함수  `MyFunction` 는 서로 다른 형식 인수를 사용하여 호출됩니다.  
  
```  
// generics_generic_function_3.cpp  
// compile with: /clr  
using namespace System;  
  
ref class MyBaseClass {  
protected:  
   generic <class ItemType>  
   ItemType MyBaseClassFunction(ItemType item) {  
      return item;  
   }  
};  
  
ref class MyClass: public MyBaseClass {  
public:  
   generic <class ItemType>  
   ItemType MyFunction(ItemType item) {  
      return MyBaseClass::MyBaseClassFunction<ItemType>(item);  
   }  
};  
  
int main() {  
   MyClass^ myObj = gcnew MyClass();  
  
   // Call MyFunction using an int.  
   Console::WriteLine("My function returned an int: {0}",  
                           myObj->MyFunction<int>(2003));  
  
   // Call MyFunction using a string.  
   Console::WriteLine("My function returned a string: {0}",  
   myObj->MyFunction<String^>("Hello generic functions!"));  
}  
```  
  
 **Output**  
  
  **함수는 int를 반환합니다: 2003**  
 **함수는 문자열을 반환 합니다: 일반 기능 안녕\!**   
## 참고 항목  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)   
 [Generics](../windows/generics-cpp-component-extensions.md)