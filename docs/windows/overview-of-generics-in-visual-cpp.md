---
title: "Visual c + +의 제네릭 개요 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- generics [C++], about generics
- default initializers [C++]
- type parameters [C++]
- constructed types
- type arguments [C++]
- constructed types, open [C++]
- open constructed types [C++]
- constructed types, closed [C++]
ms.assetid: 21f10637-0fce-4916-b925-6c86a126d3aa
caps.latest.revision: "21"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5082f603c64e796ef369044e3586ae5bfe85605a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="overview-of-generics-in-visual-c"></a>Visual C++의 제네릭 개요
제네릭은 공용 언어 런타임에서 지원하는 매개 변수화된 형식입니다. 매개 변수화된 형식은 제네릭이 사용될 때 지정되는 알 수 없는 형식 매개 변수로 정의된 형식입니다.  
  
## <a name="why-generics"></a>왜 제네릭인가?  
 C++은 템플릿을 지원하고 템플릿과 제네릭은 모두 매개 변수화된 형식을 지원하여 형식화된 컬렉션 클래스를 만듭니다. 그러나 템플릿은 컴파일 시간 매개 변수화를 제공합니다. 템플릿 정의가 포함된 어셈블리를 참조하고 해당 템플릿의 새 특수화를 만들 수는 없습니다. 컴파일되면 특수화된 템플릿은 다른 클래스나 메서드처럼 보입니다. 반면에, 제네릭은 매개 변수화된 형식이 되기 위해 런타임으로 알려진 매개 변수화된 형식으로 MSIL에서 출력됩니다. 제네릭 형식이 포함된 어셈블리를 참조하는 소스 코드는 특수화된 제네릭 형식을 만들 수 있습니다. Visual c + + 템플릿과 제네릭의 비교에 자세한 내용은 참조 하십시오. [템플릿 (Visual c + +)](../windows/generics-and-templates-visual-cpp.md)합니다.  
  
## <a name="generic-functions-and-types"></a>제네릭 함수 및 형식  
 클래스 형식은 관리되는 형식인 경우 제네릭일 수 있습니다. 이러한 경우에 대한 예로 `List` 클래스를 들 수 있습니다. 목록에 있는 개체의 형식은 형식 매개 변수입니다. 필요한 경우 한 `List` 다양 한 유형의 제네릭 사용 하기 전에 개체에 대 한 클래스는 `List` 생긴다는 **system:: object** 항목 형식으로. 하지만 그런 경우 모든 개체(잘못된 형식의 개체 포함)를 목록에서 사용할 수 있도록 허용하게 됩니다. 그러한 목록은 형식화되지 않은 컬렉션 클래스라고 합니다. 기껏해야 런타임에서 형식을 확인하고 예외를 throw할 수 있습니다. 또는 어셈블리로 컴파일되면 제네릭 품질을 잃을 수 있는 템플릿을 사용했을 수도 있습니다. 어셈블리의 소비자는 직접 템플릿의 특수화를 만들 수 없습니다. 제네릭을 사용 예를 들어 형식화 된 컬렉션 클래스를 만들 수 있습니다 `List<int>` ("int 목록"으로 읽음) 및 `List<double>` ("double 목록")에 형식화 된 적용 되도록 설계 되지 않은 컬렉션 형식을 배치 하 려 한 경우 컴파일 타임 오류가 생성할 수 있는 컬렉션입니다. 또한, 이러한 형식은 컴파일된 후 제네릭으로 남아 있습니다.  
  
 제네릭 클래스의 구문에 대 한 설명을 확인할 수 있습니다 [제네릭 클래스 (C + + /cli CLI)](../windows/generic-classes-cpp-cli.md) `.` 새 네임 스페이스 <xref:System.Collections.Generic>를 포함 하 여 매개 변수가 있는 컬렉션 형식의 집합을 도입 <xref:System.Collections.Generic.Dictionary%602>, <xref:System.Collections.Generic.List%601>및 <xref:System.Collections.Generic.LinkedList%601>합니다.  
  
 인스턴스 및 정적 클래스 멤버 함수, 대리자 및 전역 함수도 제네릭일 수 있습니다. 제네릭 함수는 함수의 매개 변수가 알 수 없는 형식이거나 함수 자체에서 제네릭 형식으로 작업해야 할 경우 필요할 수 있습니다. 대부분의 경우에서 여기서 **system:: object** 사용 했을 수 알 수 없는 개체 유형에 대 한 매개 변수로 과거에는 제네릭 형식 매개 변수 대신 사용할 수 있습니다, 좀 더 형식이 안전한 코드입니다. 함수에 사용할 수 없는 형식으로 전달하려는 시도는 컴파일 타임에 오류로 플래그가 지정될 수 있습니다. 사용 하 여 **system:: object** 부주의 한 전달 함수 매개 변수로 개체의 함수를 다루는 데 의도 되지 않은 검색할 수 없습니다, 및를 특정 형식에 알 수 없는 개체 형식을 캐스팅 하는 것은 함수 본문 및 InvalidCastException의 가능성에 대 한 계정입니다. 제네릭을 사용하여, 개체를 함수에 전달하려는 코드 시도는 형식 충돌을 일으켜서 함수 본문은 올바른 형식을 갖도록 보장됩니다.  
  
 동일한 이점은 제네릭을 기반으로 하는 컬렉션 클래스에도 적용됩니다. 과거의 컬렉션 클래스 사용 **system:: object** 컬렉션에 요소를 저장할 수 있습니다. 컬렉션에 사용되지 않는 형식의 개체 삽입은 컴파일 타임에 플래그가 지정되지 않았고 심지어 개체가 삽입될 때에도 대개 플래그 지정되지 않았습니다. 일반적으로, 개체는 컬렉션에서 액세스하는 경우 일부 다른 형식으로 캐스팅될 것입니다. 캐스팅에 실패했을 때만 예기치 않은 형식이 감지됩니다. 제네릭은 컴파일 타임에 제네릭 컬렉션의 형식 매개 변수와 일치하지 않는 (또는 암시적으로 변환) 형식을 삽입하는 코드를 감지함으로써 이 문제를 해결합니다.  
  
 구문에 대 한 참조 [제네릭 함수 (C + + /cli CLI)](../windows/generic-functions-cpp-cli.md)합니다.  
  
## <a name="terminology-used-with-generics"></a>제네릭을 사용하는 용어  
  
##### <a name="type-parameters"></a>형식 매개 변수  
 제네릭 선언에 하나 이상의 알 수 없는 형식으로 *형식 매개 변수*합니다. 형식 매개 변수는 제네릭 선언의 본문 안에 있는 형식을 나타내는 이름 입니다. 형식 매개 변수는 제네릭 선언의 본문 안에 있는 형식으로 사용됩니다. 제네릭 선언 목록에 < T\> 화 형식 매개 변수를 포함 합니다.  
  
##### <a name="type-arguments"></a>형식 인수  
 *형식 인수가* 는 제네릭이 특정 형식 또는 형식에 전문화 될 때 형식 매개 변수 대신 사용 되는 실제 유형입니다. 예를 들어, `int`는 `List<int>`의 형식 인수입니다. 값 형식과 핸들 형식은 제네릭 형식 인수로 허용 되는 유일한 형식입니다.  
  
##### <a name="constructed-type"></a>생성된 형식  
 제네릭 형식에서 생성 되는 형식으로 참조 됩니다는 *생성 된 형식*합니다. 완전히 지정 된 형식, 같은 `List<T>` 는 *개방형 생성된 형식*인 형식을 완벽 하 게 지정 하면 다음과 같이 `List<double>,` 는 *폐쇄형 생성된 형식* 또는 *특수 형식* . 개방형 생성 형식이 다른 제네릭 형식 또는 메서드 정의에 사용될 수 있고 바깥쪽 제네릭 자체가 지정될 때까지 완전히 지정되지 않습니다. 예를 들어, 다음은 제네릭에 대한 기본 클래스로 개방형 생성 형식의 사용입니다.  
  
 `// generics_overview.cpp`  
  
 `// compile with: /clr /c`  
  
 `generic <typename T>`  
  
 `ref class List {};`  
  
 `generic <typename T>`  
  
 `ref class Queue : public List<T> {};`  
  
##### <a name="constraint"></a>제약 조건  
 제약 조건은 형식 매개 변수로 사용할 수 있는 형식에 대한 제한입니다. 예를 들어, 주어진 제네릭 클래스는 지정된 클래스에서 상속되는 클래스만 허용되고 지정된 인터페이스를 구현할 수 있습니다. 자세한 내용은 참조 [제네릭 형식 매개 변수에 대 한 제약 조건 (C + + /cli CLI)](../windows/constraints-on-generic-type-parameters-cpp-cli.md)합니다.  
  
## <a name="reference-types-and-value-types"></a>참조 형식 및 값 형식  
 핸들 형식 및 값 형식을 형식 인수로 사용할 수 있습니다. 어느 한 형식이 사용될 수 있는 제네릭 정의에서 구문은 참조 형식입니다. 예를 들어는  **->**  여부는 결국 사용 되는 형식이 참조 형식 또는 값 형식이 형식 매개 변수의 형식의 멤버 액세스 연산자를 사용 합니다. 값 형식이 형식 인수로 사용되면, 런타임은 값 형식을 직접 boxing하지 않고 값 형식을 사용하는 코드를 생성합니다.  
  
 참조 형식을 제네릭 형식 인수로 사용하는 경우, 핸들 구문을 사용합니다. 값 형식을 제네릭 형식 인수로 사용할 경우, 직접 형식 이름을 사용합니다.  
  
 `// generics_overview_2.cpp`  
  
 `// compile with: /clr`  
  
 `generic <typename T>`  
  
 `ref class GenericType {};`  
  
 `ref class ReferenceType {};`  
  
 `value struct ValueType {};`  
  
 `int main() {`  
  
 `GenericType<ReferenceType^> x;`  
  
 `GenericType<ValueType> y;`  
  
 `}`  
  
## <a name="type-parameters"></a>형식 매개 변수  
 제네릭 클래스의 형식 매개 변수는 다른 식별자처럼 취급됩니다. 그러나, 형식을 알 수 없기 때문에 사용에 제한이 있습니다. 예를 들어, 이러한 멤버를 지원하기 위해 형식 매개 변수가 알려지지 않은 경우 형식 매개 변수 클래스의 멤버와 메서드를 사용할 수 없습니다. 즉, 형식 매개 변수를 통해 멤버에 액세스하려면 멤버를 포함한 형식을 형식 매개 변수의 제약 조건 목록에 추가해야 합니다.  
  
 `// generics_overview_3.cpp`  
  
 `// compile with: /clr`  
  
```  
interface class I {  
   void f1();  
   void f2();  
};  
  
ref struct R : public I {  
   virtual void f1() {}  
   virtual void f2() {}   
   virtual void f3() {}   
};  
  
generic <typename T>  
where T : I  
void f(T t) {  
   t->f1();  
   t->f2();  
   safe_cast<R^>(t)->f3();  
}  
  
int main() {  
   f(gcnew R());  
}  
```  
  
 이러한 제한은 연산자에도 적용됩니다. 제한되지 않은 제네릭 형식 매개 변수는 `==` 및 `!=` 연산자를 지원하지 않는 형식인 경우에 형식 매개 변수의 두 인스턴스를 비교하기 위해 사용하지 않습니다. 이러한 검사는 템플릿이 아닌 제네릭에 필요합니다. 제네릭은 유효하지 않은 멤버 사용을 확인하기에 너무 늦을 때, 런타임에 제약 조건을 만족시키는 클래스를 사용하여 특수화될 수 있기 때문입니다.  
  
 형식 매개 변수의 기본 인스턴스는 `()` 연산자를 사용하여 만들어질 수 있습니다. 예:  
  
 `T t = T();`  
  
 여기서 `T`는 제네릭 클래스 또는 메서드 정의에서 형식 매개 변수로, 변수를 기본값으로 초기화합니다. `T`가 ref 클래스인 경우, null 포인터가 됩니다. `T`가 값 클래스인 경우, 개체가 0으로 초기화됩니다. 이 라고는 *기본 이니셜라이저*합니다.  
  
## <a name="see-also"></a>참고 항목  
 [제네릭](../windows/generics-cpp-component-extensions.md)