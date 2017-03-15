---
title: "Overview of Generics in Visual C++ | Microsoft Docs"
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
  - "generics [C++], about generics"
  - "default initializers [C++]"
  - "type parameters [C++]"
  - "constructed types"
  - "type arguments [C++]"
  - "constructed types, open [C++]"
  - "open constructed types [C++]"
  - "constructed types, closed [C++]"
ms.assetid: 21f10637-0fce-4916-b925-6c86a126d3aa
caps.latest.revision: 21
caps.handback.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Overview of Generics in Visual C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

제네릭은 공용 언어 런타임에서 지원 하는 매개 변수가 있는 형식입니다.  매개 변수화 된 형식은 제네릭이 사용될 때 지정 하는 알 수 없는 형식 매개 변수를 사용 하여 정의 하는 형식 입니다.  
  
## 왜 제네릭인가?  
 C\+\+은 템플릿을 지원하고 템플릿과 제네릭은 입력된 컬렉션 클래스를 만들 수 있는 매개 변수가 있는 형식을 지원 합니다.  그러나, 템플릿은 컴파일할 매개 변수화를 제공합니다.  템플릿 정의가 포함된 어셈블리를 참조 하고 새 템플릿 특수화를 만들 수 없습니다.  일단 컴파일되면, 특수 템플릿은 클래스 또는 메서드 처럼 보입니다.  반면에, 제네릭은 매개 변수화 된 형식이 되기 위해 런타임으로 알려진 매개 변수가 있는 형식으로 MSIL에서 출력 됩니다. 제네릭 형식이 포함된 어셈블리를 참조 하는 소스 코드는 특수화 된 제네릭 형식을 만들 수 있습니다.  Visual C\+\+ 템플릿과 generic의 비교에 대한 자세한 내용은 [Generics and Templates \(Visual C\+\+\)](../windows/generics-and-templates-visual-cpp.md)를 참조하십시오.  
  
## 제네릭 함수 및 형식  
 클래스 형식은 관리 되는 형식인 한 제네릭일 수 있습니다.  이 예제는 `List` 클래스입니다.  목록에 있는 개체의 형식은 형식 매개 변수입니다.  제네릭이 항목 형식으로 **System::Object**를 취하는 `List` 를 갖기 전에 다른 형식의 개체에 `List` 클래스를 필요로 합니다.  하지만 \(잘못된 형식의 개체를 포함하여\) 모든 개체 목록에서 사용할 수 있도록 허용 합니다.  형식화 되지 않은 컬렉션 클래스는 이러한 목록을 호출 됩니다.  기껏해야 런타임에서 형식을 확인 하고 예외를 throw 없습니다.  또는, 제네릭 품질이 일단 어셈블리로 컴파일되어 손실되면 템플릿을 사용 합니다.  어셈블리의 소비자는 템플릿의 특수화를 만들 수 없습니다.  제네릭을 사용 하면 예를 들어 만약 컬렉션이 입력된 컬렉션으로 적용되게 설계 되지 않은 형식을 두려고 할 경우 컴파일 타임 오류를 생성하는 `List<int>` \("int 목록" 이라고 읽음\)와  `List<double>` \("더블의 목록"\) 과 같은 형식화 된 컬렉션 클래스를 만들 수 있습니다.  또한, 컴파일된 후 이러한 형식은 제네릭으로 남아 있습니다.  
  
 제네릭 클래스의 구문에 대한 설명은 [Generic Classes \(C\+\+\/CLI\)](../windows/generic-classes-cpp-cli.md)`.` 새 네임스페이스, <xref:System.Collections.Generic>, 은 <xref:System.Collections.Generic.Dictionary%602>, <xref:System.Collections.Generic.List%601> 및 <xref:System.Collections.Generic.LinkedList%601> 이 포함된 매개 변수화 된 컬렉션 형식의 집합을 소개합니다.  자세한 내용은 [.NET Framework 클래스 라이브러리의 제네릭](../Topic/Generics%20in%20the%20.NET%20Framework%20Class%20Library%20\(C%23%20Programming%20Guide\).md)를 참조하십시오.  
  
 인스턴스 및 정적 클래스 멤버 함수, 대리자 및 전역 함수는 제네릭일 수도 있습니다.  제네릭 함수는 함수의 매개 변수가 알 수 없는 형식 또는 함수 자체에서 제네릭 형식으로 작업 해야 할 경우 필요합니다.  **System::Object** 가 과거에 알 수 없는 개체 형식의 매개 변수로 사용되는 경우, 형식이 안전한 코드를 사용하여 제네릭 형식 매개 변수가 대신 사용됩니다.  함수가 컴파일 타임에 오류로 플래그가 지정되지 않은 함수 형식에서 시도가 전달 됩니다.  함수 매개 변수로 **System::Object** 를 사용하여, 함수가 처리 하려고 하지 않았던 개체를 실수로 전달하는 것은 발견 되지 않고, 알려 지지 않은 개체 형식을 함수 본문에 특정 형식으로 캐스팅 하고 InvalidCastException 가능성을 고려 합니다.  제네릭을 사용하여, 개체를 함수에 전달하려고 하는 코드 시도는 형식 충돌을 일으켜서 함수 본문은 올바른 형식을 갖도록 보장합니다.  
  
 동일한 이점을 기반으로 제네릭 컬렉션 클래스에 적용 됩니다.  과거의 컬렉션 클래스는 **System::Object** 를 사용하여 컬렉션에 요소를 저장할 수 있습니다.  컬렉션이 설계 되지 않은 컬렉션의 형식 개체 삽입은 컴파일 타임에 플래그 되지 않고, 심지어 개체가 삽입 될 때 플래그 되지 않습니다.  일반적으로, 개체는 컬렉션에 액세스 하는 경우 일부 다른 형식으로 캐스팅 될 것입니다.  캐스팅에 실패 했을 때만 예기치 않은 형식이 감지 됩니다.  제네릭은 컴파일 타임에 제네릭 컬렉션의 형식 매개 변수와 일치하지 않는 형식을 삽입하는 코드를 감지 함으로써 이 문제를 해결 합니다.  
  
 구문에 대한 설명은 다음을 참조하십시오. [Generic Functions \(C\+\+\/CLI\)](../windows/generic-functions-cpp-cli.md).  
  
## 제네릭을 사용 하는 용어  
  
##### 형식 매개 변수  
 제네릭 선언에는 *type parameters* 라는 지정되지 않은 형식이 하나 이상 들어 있습니다.  형식 매개 변수는 제네릭 선언의 본문 안에 있는 형식을 나타내는 이름 입니다.  형식 매개 변수는 제네릭 선언의 본문 안에 있는 형식으로 사용됩니다.  \<T\> 목록을 위한 제네릭 선언은 형식 매개 변수 T를 포함 합니다.  
  
##### 형식 인수  
 *형식 인수* 는 제네릭이 특정 형식 또는 형식에 전문화 될 때 형식 매개 변수 대신 사용되는 실제 형식입니다.  예를 들어, `int` 는 `List<int>` 의 형식 인수 입니다.  값 형식과 핸들 형식을 제네릭 형식 인수로 허용 되는 유일한 형식 입니다.  
  
##### 생성된 형식  
 제네릭 형식에서 생성 되는 형식은 *생성된 형식*으로 참조 됩니다.  `List<T>`가 *개방 생성된 형식*과 같이 형식을 완전히 지정되지 않습니다. `List<double>,`는 *폐쇄형 생성된 형식* 또는 *특수 형식* 과 같이 완전히 지정된 형식입니다.  개방형 생성된 형식이 다른 제네릭 형식 또는 메서드 정의에 사용 될 수 있고 바깥쪽 제네릭 그 자체가 지정될 때 까지 완전히 지정되지 않습니다.  예를 들어, 다음은 제네릭에 대한 기본 클래스로 개방형 생성된 형식의 사용입니다.  
  
 `// generics_overview.cpp`  
  
 `// compile with: /clr /c`  
  
 `generic <typename T>`  
  
 `ref class List {};`  
  
 `generic <typename T>`  
  
 `ref class Queue : public List<T> {};`  
  
##### 제약 조건  
 제약 조건은 형식 매개 변수로 사용할 수 있는 형식에 대한 제한입니다.  예를 들어, 주어진 제네릭 클래스는 지정된 클래스에서 상속 되는 클래스에만 적용 하거나 지정된 인터페이스를 구현할 수 없습니다.  자세한 내용은 [Constraints on Generic Type Parameters \(C\+\+\/CLI\)](../windows/constraints-on-generic-type-parameters-cpp-cli.md)을 참조하십시오.  
  
## 참조 형식과 값 형식  
 핸들 형식 및 값 형식을 형식 인수로 사용할 수 있습니다.  제네릭 정의에서, 어느 형식에서 사용될 경우에서도, 구문은 참조 형식 입니다.  예를 들어, **\-\>** 연산자는 형식이 결국 참조 형식 또는 값 형식에서 사용되는 여부에 관계 없이 형식 매개 변수의 형식의 멤버에 액세스하는 데 사용됩니다.  값 형식이 형식 인수로 사용 되면, 런타임은 값 형식을 직접 boxing 하지 않고 값 형식을 사용하는 코드를 생성 합니다.  
  
 참조 형식을 제네릭 형식 인수로 사용 하는 경우, 핸들 구문을 사용 합니다.  값 형식을 제네릭 형식 인수로 사용 할 경우, 직접 형식 이름을 사용 합니다.  
  
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
  
## 형식 매개 변수  
 제네릭 클래스의 형식 매개 변수는 다른 식별자 처럼 취급 됩니다.  그러나, 형식을 알 수 없기 때문에, 사용 상 제한이 있습니다.  예를 들어, 이러한 멤버를 지원 하기 위해 형식 매개 변수가 알려지지 않은 경우 형식 매개 변수 클래스의 멤버와 메서드에 사용할 수 없습니다.  즉, 형식 매개 변수를 통해 멤버에 액세스 하려면 멤버 형식 매개 변수의 제약 조건 목록에 포함된 형식을 추가 해야 합니다.  
  
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
  
 이러한 제한은 연산자에 적용 됩니다.  제한 되지 않은 제네릭 형식 매개 변수는 `==` 및 `!=` 연산자를 지원하지 않는 형식인 경우에 형식 매개 변수의 두 인스턴스를 비교하기 위해 사용하지 않습니다.  이러한 검사는 템플릿이 아닌 제네릭에 필요 합니다. 왜냐하면 제네릭은 유효 하지 않은 멤버 사용을 확인하기에 너무 늦을 때, 런타임에 제약 조건을 만족 시키는 클래스를 사용하여 특수화되기 때문입니다.  
  
 형식 매개 변수의 기본 인스턴스는 `()` 연산자를 사용하여 만들어 질 수 있습니다.  예를 들면 다음과 같습니다.  
  
 `T t = T();`  
  
 여기서 `T` 는 제네릭 클래스 또는 메서드 정의에서 변수를 기본값으로 초기화하는 형식 매개 변수 입니다.  `T` 가 ref 클래스인 경우, null 포인터가 됩니다; `T` 가 값 클래스인 경우, 개체가 0으로 초기화 됩니다.  이것은 *기본 이니셜라이저*으로 불립니다.  
  
## 참고 항목  
 [Generics](../windows/generics-cpp-component-extensions.md)