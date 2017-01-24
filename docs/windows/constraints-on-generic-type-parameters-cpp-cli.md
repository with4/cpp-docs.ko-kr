---
title: "Constraints on Generic Type Parameters (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "where"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "where keyword [C++]"
  - "constraints, C++"
ms.assetid: eb828cc9-684f-48a3-a898-b327700c0a63
caps.latest.revision: 25
caps.handback.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Constraints on Generic Type Parameters (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

제네릭 형식 또는 메서드 선언에는 제약 조건이 있는 형식 매개 변수를 한정할 수 있습니다.  제약 조건은 형식 인수로 사용 되는 형식이 충족 해야 하는 요구 사항입니다.  예를 들어, 형식 인수가 특정 인터페이스를 구현 하거나 특정 클래스에서 상속 해야 제한할 수 있습니다.  
  
 제약 조건은 선택적입니다; 해당 매개 변수를 지정하지 않는 것은 <xref:System.Object>에 매개 변수에 대한 제약을 하는 것과 동일합니다.  
  
## 구문  
  
```  
  
where type-parameter: constraint list  
```  
  
#### 매개 변수  
 *형식 매개 변수*.  
 제한 되는 형식 매개 변수 중 하나입니다.  
  
 *제약 조건 목록*  
 *제약 조건 목록*은 제약 조건의 쉼표로 구분된 목록입니다.  목록은 형식 매개 변수로 구현해야 하는 인터페이스를 포함할 수 있습니다.  
  
 목록 클래스를 포함할 수도 있습니다.  기본 클래스 제약 조건을 만족 하려면 형식 인수에 대한 제약 조건과 같은 클래스나 제약 조건에서 파생해야 합니다.  
  
 `gcnew()` 을 지정하여 형식 인수가 매개 변수 없는 public 생성자를 가져야한다는 것을 나타냅니다; 또는  `ref class` 를 지정하여 형식 인수가 클래스, 인터페이스, 대리자 또는 배열 형식이 포함된 참조 형식이어야 한다는 것을 나타내거나 또는  `value class` 을 지정하여 유형을 나타내는 인수가 값 형식이어야 한다는 점을 나타냅니다.  Nullable\<T\>를 제외한 임의의 값 형식을 지정할 수 있습니다.  
  
 제네릭 매개 변수 제약 조건으로 지정할 수도 있습니다.  구속 된 유형에 대해 제공되는 형식 인수는 또는 제약 조건의 유형에서 파생되어야 합니다.  이 naked 형식 제약 조건을 이라고 합니다.  
  
## 설명  
 Constraint 절은  형식 매개 변수에 콜론 뒤에 \(**::**\) **위치** 로 이루어져 있습니다. 제약 조건을 형식 매개 변수에 제한의 특성을 지정하고 있습니다.  **where** 는 대\/소문자를 구분하는 키워드입니다. 자세한 내용은 [상황에 맞는 키워드](../windows/context-sensitive-keywords-cpp-component-extensions.md)를 참조하십시오.  공백으로 여러 개의 **where** 절을 구분합니다.  
  
 제약 조건은 제네릭 형식 또는 메서드의 인수로 사용할 수있는 형식에 대한 제한을 배치 매개 변수를 입력하기 위해 적용됩니다.  
  
 클래스 및 인터페이스 제약 인수 형식이 될 수 또는 지정된 클래스에서 상속 또는 지정된 인터페이스를 구현해야 함을 지정합니다.  
  
 제네릭 형식 또는 메서드에 대한 제약 조건의 적용은 제한된 유형의 알려진 기능을 활용하기 위해 해당 종류 나 방법에 코드를 할 수 있습니다.  예를 들어, 다음과 같이 형식 매개 변가수 **IComparable\<T\>** 인터페이스를 구현하도록 제네릭 클래스를 선언할 수 있습니다.  
  
```  
// generics_constraints_1.cpp  
// compile with: /c /clr  
using namespace System;  
generic <typename T>  
where T : IComparable<T>  
ref class List {};  
```  
  
 이 제약 조건은 컴파일 타임에  `T` 에 사용되는 형식 인수가  `IComparable<T>` 을 구현하는 것을 필요로합니다.  **CompareTo**가 호출되는 것 처럼 인터페이스 메서드를 허용합니다.  캐스트는 인터페이스 메서드를 호출하는 형식 매개 변수의 인스턴스에 필요하지 않습니다.  
  
 형식 인수가 클래스의 정적 메서드는 형식 매개 변수를 통해 호출할 수 없습니다. 실제 명명된 형식을 통해서만 호출할 수 있습니다.  
  
 제약조건은  `int`  또는  **double** 기본 제공 형식을 포함하는 값 형식일 수 없습니다 .  값 형식은 파생 클래스를 가질 수 없기 때문에, 하나의 클래스 만 적 제약 조건을 만족시킬 수있을 것입니다.  이 경우에는 제네릭 특정 값 형식으로 대체 형식 매개 변수를 사용하여 다시 작성할 수 있습니다.  
  
 제약 조건은 알 수없는 형식의 방법이나 인터페이스를 지원하는 것을 의미하지 않는 한 컴파일러는 방법이나 알 수없는 형식의 다른 기능의 사용을 허용하지 않습니다. 때문에 제약 조건은 어떤 경우에 필요합니다.  
  
 동일한 형식 매개 변수에 여러 제약 조건은 쉼표로 구분된 목록에 지정할 수 있습니다.  
  
```  
// generics_constraints_2.cpp  
// compile with: /c /clr  
using namespace System;  
using namespace System::Collections::Generic;  
generic <typename T>  
where T : List<T>, IComparable<T>  
ref class List {};  
```  
  
 형식 매개 변수가 여러 개이면  **where** 절을 각 형식 매개 변수마다 하나씩 사용합니다.  예를 들면 다음과 같습니다.  
  
```  
// generics_constraints_3.cpp  
// compile with: /c /clr  
using namespace System;  
using namespace System::Collections::Generic;  
  
generic <typename K, typename V>  
   where K: IComparable<K>  
   where V: IComparable<K>  
ref class Dictionary {};  
```  
  
 요약 하면 다음 규칙에 따라 코드에서 제약 조건을 사용합니다.  
  
-   여러 제약 조건이 표시되면, 제약은 순서에 상관없이 나열 될 수 있습니다.  
  
-   제약 조건은 추상 기본 클래스 같은 클래스 종류일 수 있습니다.  그러나 sealed 클래스 또는 값 형식 제약 조건이 될 수 없습니다.  
  
-   제약 조건 자체가 형식 매개 변수가되지 않을 수 있지만 개방형 생성 형식의 형식 매개 변수를 포함할 수 있습니다.  예를 들면 다음과 같습니다.  
  
    ```  
    // generics_constraints_4.cpp  
    // compile with: /c /clr  
    generic <typename T>  
    ref class G1 {};  
  
    generic <typename Type1, typename Type2>  
    where Type1 : G1<Type2>   // OK, G1 takes one type parameter  
    ref class G2{};  
    ```  
  
## 예제  
 다음 예제에서는 제약 조건을 사용하여 형식 매개 변수에서 인스턴스 메서드를 호출하는 방법을 보여줍니다.  
  
```  
// generics_constraints_5.cpp  
// compile with: /clr  
using namespace System;  
  
interface class IAge {  
   int Age();  
};  
  
ref class MyClass {  
public:  
   generic <class ItemType> where ItemType : IAge   
   bool isSenior(ItemType item) {  
      // Because of the constraint,  
      // the Age method can be called on ItemType.  
      if (item->Age() >= 65)   
         return true;  
      else  
         return false;  
   }  
};  
  
ref class Senior : IAge {  
public:  
   virtual int Age() {  
      return 70;  
   }  
};  
  
ref class Adult: IAge {  
public:  
   virtual int Age() {  
      return 30;  
   }  
};  
  
int main() {  
   MyClass^ ageGuess = gcnew MyClass();  
   Adult^ parent = gcnew Adult();  
   Senior^ grandfather = gcnew Senior();  
  
   if (ageGuess->isSenior<Adult^>(parent))  
      Console::WriteLine("\"parent\" is a senior");  
   else  
      Console::WriteLine("\"parent\" is not a senior");  
  
   if (ageGuess->isSenior<Senior^>(grandfather))  
      Console::WriteLine("\"grandfather\" is a senior");  
   else  
      Console::WriteLine("\"grandfather\" is not a senior");  
}  
```  
  
  **"부모"를 선임하지 않습니다.**  
**"할아버지"는 선임입니다.**   
## 예제  
 제네릭 형식 매개 변수를 제약 조건으로 사용하면 naked 형식 제약이라고 합니다.  고유 한 형식 매개 변수와 멤버 함수가 포함하는 형식의 형식 매개 변수에 해당 매개 변수를 제한 할 필요가있을 때 Naked 유형 제약이 유용합니다.  
  
 다음 예제에서 T는 Add 메서드의 컨텍스트에서 naked 형식 제약 조건입니다.  
  
 Naked 형식 매개 변수는 제네릭 클래스 정의에서 사용할 수 있습니다.  컴파일러에서는 naked 형식 매개 변수가 <xref:System.Object>에서 파생된다는 점을 제외하고는 이 제약 조건에 대해 어떠한 정보도 알 수 없으므로 naked 형식 제약과 제네릭 클래스를 함께 사용할 필요는 거의 없습니다.  두 형식 매개 변수 사이의 상속 관계를 적용 할 수있는 시나리오에서 제네릭 클래스에 naked 형식 제약 조건을 사용합니다.  
  
```  
// generics_constraints_6.cpp  
// compile with: /clr /c  
generic <class T>  
ref struct List {  
   generic <class U>  
   where U : T  
   void Add(List<U> items)  {}  
};  
  
generic <class A, class B, class C>  
where A : C  
ref struct SampleClass {};  
```  
  
## 참고 항목  
 [Generics](../windows/generics-cpp-component-extensions.md)