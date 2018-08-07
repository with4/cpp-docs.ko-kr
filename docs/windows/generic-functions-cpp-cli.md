---
title: 제네릭 함수 (C + + /cli CLI) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- functions [C++], generic
- generic methods
- generics [C++], functions
- methods [C++], generic
- generic functions
ms.assetid: 8e409364-58f9-4360-b486-e7d555e0c218
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 40f79bc6afe47bfed92d096dace59ef97eed68e1
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/06/2018
ms.locfileid: "39568880"
---
# <a name="generic-functions-ccli"></a>제네릭 함수(C++/CLI)
제네릭 함수는 형식 매개 변수를 사용 하 여 선언 된 함수가입니다. 호출 되 면 실제 형식은 형식 매개 변수 대신 사용 됩니다.  
  
## <a name="all-platforms"></a>모든 플랫폼  
 **주의**  
  
 이 기능은 모든 플랫폼에 적용 되지 않습니다.  
  
## <a name="windows-runtime"></a>Windows 런타임  
 **주의**  
  
 이 기능은 Windows 런타임에서 지원 되지 않습니다.  
  
### <a name="requirements"></a>요구 사항  
 컴파일러 옵션: `/ZW`  
  
## <a name="common-language-runtime"></a>공용 언어 런타임 
 제네릭 함수는 형식 매개 변수를 사용 하 여 선언 된 함수가입니다. 호출 되 면 실제 형식은 형식 매개 변수 대신 사용 됩니다.  
  
### <a name="syntax"></a>구문  
  
```  
[attributes] [modifiers]  
return-type identifier<type-parameter identifier(s)>  
[type-parameter-constraints clauses]  
  
([formal-parameters])  
{function-body}  
```  
  
### <a name="parameters"></a>매개 변수 
  
 *특성* (선택 사항)  
 추가 선언 정보입니다. 특성 및 특성 클래스에 대 한 자세한 내용은 특성을 참조 하세요.  
  
 *한정자* (선택 사항)  
 정적 같은 함수에 대 한 한정자입니다.  **가상** 가상 메서드는 제네릭 수 있으므로 허용 되지 않습니다.  
  
 *반환 형식*  
 메서드에서 반환하는 형식입니다. 반환 형식이 void 인 경우 반환 값이 없는 경우 필요  
  
 *identifier*  
 함수 이름.  
  
 *형식 매개 변수 식별자*  
 쉼표로 구분 된 식별자 목록입니다.  
  
 *정식 매개 변수* (선택 사항)  
 매개 변수 목록입니다.  
  
 *형식 매개 변수-제약 조건 절*  
 이 형식 인수로 사용할 수 있는 형식에서 지정 하는 제한 하며에 지정 된 폼 [제네릭 형식 매개 변수에 대 한 제약 조건 (C + + CLI)](../windows/constraints-on-generic-type-parameters-cpp-cli.md)합니다.  
  
 *함수 본문*  
 형식 매개 변수 식별자를 참조할 수 있는 메서드의 본문입니다.  
  
### <a name="remarks"></a>설명  
  
 제네릭 함수는 제네릭 형식 매개 변수를 사용 하 여 선언 된 함수입니다. 메서드는 클래스, 구조체 또는 독립 실행형 함수에 있을 수 있습니다. 단일 제네릭 선언에는 암시적으로 함수를 다른 실제 형식의 제네릭 형식 매개 변수에 대 한 대체만 다르고 패밀리를 선언 합니다.  
  
 Visual c + +에서 클래스 또는 구조체 생성자를 제네릭 형식 매개 변수를 사용 하 여 선언할 수 없습니다.  
  
 를 호출 하는 경우 제네릭 형식 매개 변수는 실제 형식으로 대체 됩니다. 템플릿 함수 호출과 유사 구문을 사용 하 여 꺾쇠 괄호에 실제 형식은 명시적으로 지정할 수 있습니다. 형식 매개 변수 없이 호출 되 면 컴파일러는 함수 호출에 제공 하는 매개 변수를 실제 형식을 유추 하려고 합니다. 사용 된 매개 변수에서 원하는 형식 인수를 추론할 수 없으므로, 컴파일러는 오류를 보고 합니다.  
  
### <a name="requirements"></a>요구 사항  
 컴파일러 옵션: `/clr`  
  
### <a name="examples"></a>예제  
 **예제**  
  
 다음 코드 예제는 제네릭 함수를 보여 줍니다.  
  
```cpp  
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
  
 제네릭 함수 서명 또는 인자 수, 함수에 형식 매개 변수의 개수에 따라 오버 로드할 수 있습니다. 또한 제네릭 함수도 함수는 일부 형식 매개 변수에서과 다릅니다. 동일한 이름의 제네릭이 아닌 함수를 사용 하 여 오버 로드할 수 있습니다. 예를 들어, 다음 함수를 오버 로드할 수 있습니다.  
  
```cpp  
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
  
 다음 예제에서는 배열에서 첫 번째 요소를 찾는 제네릭 함수를 사용 합니다. 선언 `MyClass`, 기본 클래스에서 상속 하는 `MyBaseClass`합니다. `MyClass` 제네릭 함수를 포함 `MyFunction`, 다른 제네릭 함수를 호출 하는 `MyBaseClassFunction`, 기본 클래스 내에서. `main`, 제네릭 함수 `MyFunction`, 다양 한 형식 인수를 사용 하 여 호출 됩니다.  
  
```cpp  
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
  
 **출력**  
  
```Output  
My function returned an int: 2003  
My function returned a string: Hello generic functions!  
```  
  
## <a name="see-also"></a>참고 항목  
 [런타임 플랫폼용 구성 요소 확장명](../windows/component-extensions-for-runtime-platforms.md)   
 [제네릭](../windows/generics-cpp-component-extensions.md)