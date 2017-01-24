---
title: "Generic Classes (C++/CLI) | Microsoft Docs"
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
  - "classes [C++], generic"
  - "generic classes [C++], about generic classes"
  - "data types [C++], generic"
  - "generic classes"
  - "generics [C++], declaring generic classes"
ms.assetid: 0beb99e1-1ec4-4fee-9836-ce9657d67a3a
caps.latest.revision: 33
caps.handback.revision: 31
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Generic Classes (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

제네릭 클래스는 다음 형식을 사용하여 선언됩니다.  
  
## 구문  
  
```  
[attributes]  
generic <class-key type-parameter-identifier(s)>  
[constraint-clauses]  
[accessibility-modifiers] ref class identifier  [modifiers]  
[: base-list]   
{  
   class-body  
} [declarators] [;]  
```  
  
## 설명  
 위의 구문에는 다음과 같은 용어가 사용 됩니다.  
  
 `attributes`\(선택적 요소\)  
 추가 선언 정보입니다.  특성 및 특성 클래스에 대한 자세한 내용은 특성을 참조 하십시오.  
  
 *클래스 키*  
 `class` 또는 `typename` 입니다.  
  
 *형식\-매개 변수\-식별자*,  
 형식 매개 변수의 이름을 지정 하는 식별자의 쉼표로 구분 된 목록입니다.  
  
 *제약 조건 절*  
 형식 매개 변수에 대한 제약 조건을 지정 하는 **where** 절\(쉼표 구분 없습니다\) .  이 형식을 사용합니다.  
  
 `where`  *type\-parameter\-identifier*  `:`  *constraint\-list*  `...`  
  
 *제약 조건 목록*  
 *class\-or\-interface*\[`,` *...*\]  
  
 *표시 한정자*  
 제네릭 클래스에 대한 액세스가능성 한정자입니다.  [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]인 경우에, 사용할 수 있는 유일한 한정자는 `private`입니다.  공용 언어 런타임에서, 허용된 한정자는 `private` 와 `public`입니다.  
  
 *identifier*  
 제네릭 클래스의 이름은 유효한 C\+\+ 식별자입니다.  
  
 *한정자*\(선택적\)  
 허용된 한정자는 `sealed` 및  **추상**을 포함합니다.  
  
 *기본 목록*  
 하나의 기본 클래스와 포함 하는 목록의 인터페이스 목록이며 모두 쉼표로 구분됩니다.  
  
 *클래스 본문*  
 클래스 본문, 포함하는 필드, 멤버 함수 등.  
  
 *선언자*  
 이 형식의 변수를 선언 합니다.  For example: `^`*identifier*`,` ...\]  
  
 이러한 제네릭 클래스를 선언할 수 있습니다 \(키워드 **class**는 **typename** 대신 사용할 수 있습니다\).  이 예제에서,  `ItemType`, `KeyType` 및 `ValueType` 은 지점에 지정된 형식을 알 수 없는 형식입니다.  `HashTable<int, int>` 는 `HashTable<KeyType, ValueType>`의 제너릭 형식의 생성 형식입니다.  단일 제네릭 형식에서 생성된 다른 형식의 숫자를 생성할 수 있습니다.  제네릭 클래스에서 생성된 생성된 형식은 다른 ref 클래스 형식과 마찬가지로 취급 됩니다.  
  
```  
// generic_classes_1.cpp  
// compile with: /clr  
using namespace System;  
generic <typename ItemType>  
ref struct Stack {  
   // ItemType may be used as a type here  
   void Add(ItemType item) {}  
};  
  
generic <typename KeyType, typename ValueType>  
ref class HashTable {};  
  
// The keyword class may be used instead of typename:  
generic <class ListItem>  
ref class List {};  
  
int main() {  
   HashTable<int, Decimal>^ g1 = gcnew HashTable<int, Decimal>();  
}  
```  
  
 값 형식 \(`int` 또는 `double`, 또는 사용자 정의 값 형식과 같은 기본 제공 형식\) 및 참조 형식은 제네릭 형식 인수로 사용할 수 있습니다.  제네릭 정의에서 구문 같은 관계입니다.  구문적으로, 알 수 없는 형식은 참조 형식 처럼 취급 됩니다.  그러나, 런타임은 형식이 실제로 값 형식으로 사용되고 멤버에게 직접 액세스하는 적절한 생성된 코드를 대신할 지 결정할 수 있습니다.  제네릭 형식 인수로 사용 되는 값 형식은 boxed 되지 않았고 따라서 boxing과 관련된 성능 저하를 발생 하지 않습니다.  제네릭의 본문에서 사용 된 구문은 **.** 대신 **T^** 과 '**\-\>**' 이어야 합니다.  형식 매개 변수로 [ref new, gcnew](../windows/ref-new-gcnew-cpp-component-extensions.md) 사용은 만약 형식 인수가 값 형식이라면 값 형식의 간단한 생성으로서 런타임을 적절하게 해석할 수 있습니다.  
  
 제네릭 클래스를 형식 매개변수로 쓰이는 형식에 [Constraints on Generic Type Parameters \(C\+\+\/CLI\)](../windows/constraints-on-generic-type-parameters-cpp-cli.md) 로 선언될 수 있습니다.  다음 예제에서는  \\`ItemType` 의 어느 형식도 `IItem` 인터페이스를 구현해야 합니다.  예를 들어  `IItem`  을 구현 하지 않는 `int` 사용 시도는 제약 조건을 만족하지 않는 형식 인수이기 때문에 컴파일 타임 오류가 발생합니다.  
  
```  
// generic_classes_2.cpp  
// compile with: /clr /c  
interface class IItem {};  
generic <class ItemType>  
where ItemType : IItem  
ref class Stack {};  
```  
  
 동일한 네임 스페이스의 제네릭 클래스는 형식 매개변수의 종류 또는 수만 변경하여 오버 로드 할 수 없습니다.  그러나, 다른 네임 스페이스에 거주 하는 각 클래스인 경우, 오버 로드 할 수 있습니다.  예를 들어, 다음 두 클래스를 생각해봅니다. `A` 및 `B`의 `MyClass` 및 `MyClass<ItemType>`.  두 개의 클래스는 세 번째 네임 스페이스 C에서 오버 로드될 수 있습니다.  
  
```  
// generic_classes_3.cpp  
// compile with: /clr /c  
namespace A {  
   ref class MyClass {};  
}  
  
namespace B {  
   generic <typename ItemType>   
   ref class MyClass2 { };  
}  
  
namespace C {  
   using namespace A;  
   using namespace B;  
  
   ref class Test {  
      static void F() {  
         MyClass^ m1 = gcnew MyClass();   // OK  
         MyClass2<int>^ m2 = gcnew MyClass2<int>();   // OK  
      }  
   };  
}  
```  
  
 기본 인터페이스와 기본 클래스는 형식 매개변수가 될 수 없습니다.  그러나, 다음과 같은 경우 인수로 기본 클래스는 형식 매개 변수를 포함할 수 있습니다.  
  
```  
// generic_classes_4.cpp  
// compile with: /clr /c  
generic <typename ItemType>  
interface class IInterface {};  
  
generic <typename ItemType>  
ref class MyClass : IInterface<ItemType> {};  
```  
  
 생성자와 소멸자는 각 개체 인스턴스에 대해 한 번만 실행 됩니다 \(일반적으로\). 정적 생성자는 생성 된 각 형식에 대해 한 번씩 실행 됩니다.  
  
## 제네릭 클래스의 필드  
 이 단원에서는 제네릭 클래스에 있는 정적 필드와 인스턴스의 사용을 설명합니다.  
  
### 인스턴스 변수  
 제네릭 클래스의 인스턴스 변수는 형식과 바깥쪽 클래스의 형식 매개 변수를 포함 하는 변수 이니셜라이저를 가질 수 있습니다.  
  
## 예제  
 다음 예제에서는 제네릭 클래스 MyClass\<ItemType\> 의 세 가지 다른 인스턴스를 적절한 형식 인수로 사용 하여 만들어집니다 \(`int`, **double**, 및 **string**\).  
  
```  
// generics_instance_fields1.cpp  
// compile with: /clr  
// Instance fields on generic classes  
using namespace System;  
  
generic <typename ItemType>  
ref class MyClass {  
// Field of the type ItemType:  
public :  
   ItemType field1;  
   // Constructor using a parameter of the type ItemType:  
   MyClass(ItemType p) {  
     field1 = p;   
   }  
};  
  
int main() {  
   // Instantiate an instance with an integer field:  
   MyClass<int>^ myObj1 = gcnew MyClass<int>(123);  
   Console::WriteLine("Integer field = {0}", myObj1->field1);  
  
   // Instantiate an instance with a double field:  
   MyClass<double>^ myObj2 = gcnew MyClass<double>(1.23);  
   Console::WriteLine("Double field = {0}", myObj2->field1);  
  
   // Instantiate an instance with a String field:  
   MyClass<String^>^ myObj3 = gcnew MyClass<String^>("ABC");  
   Console::WriteLine("String field = {0}", myObj3->field1);  
   }  
```  
  
  **정수 필드 \= 123**  
**이중 필드 \= 1.23**  
**문자열 필드 \= ABC**   
## 정적 변수  
 새 제네릭 형식 만들기에서, 정적 변수의 모든 인스턴스를 새로 만들고 해당 형식에 대한 정적 생성자가 실행 됩니다.  
  
 정적 변수는 바깥쪽 클래스의 형식 매개 변수를 사용할 수 있습니다.  
  
## 예제  
 다음 예제에서는 제네릭 클래스에는 정적 생성자 및 정적 필드 사용 하는 방법을 보여 줍니다.  
  
```  
// generics_static2.cpp  
// compile with: /clr  
using namespace System;  
  
interface class ILog {  
   void Write(String^ s);  
};  
  
ref class DateTimeLog : ILog {  
public:  
   virtual void Write(String^ s) {  
      Console::WriteLine( "{0}\t{1}", DateTime::Now, s);  
   }  
};  
  
ref class PlainLog : ILog {  
public:  
   virtual void Write(String^ s) { Console::WriteLine(s); }  
};  
  
generic <typename LogType>  
where LogType : ILog  
ref class G {  
   static LogType s_log;  
  
public:  
   G(){}  
   void SetLog(LogType log) { s_log = log; }  
   void F() { s_log->Write("Test1"); }  
   static G() { Console::WriteLine("Static constructor called."); }     
};  
  
int main() {  
   G<PlainLog^>^ g1 = gcnew G<PlainLog^>();  
   g1->SetLog(gcnew PlainLog());  
   g1->F();  
  
   G<DateTimeLog^>^ g2 = gcnew G<DateTimeLog^>();  
   g2->SetLog(gcnew DateTimeLog());  
  
   // prints date  
   // g2->F();  
}  
```  
  
  **정적 생성자가 호출 됩니다.**  
**정적 생성자가 호출 됩니다.**  
**정적 생성자가 호출 됩니다.**  
**테스트 1**   
## 제네릭 클래스의 메서드  
 제네릭 클래스의 메서드는 제네릭이 스스로 될 수 있습니다. 제네릭이 아닌 메서드 클래스 형식 매개 변수로 암시적으로 매개 변수화 됩니다.  
  
 제네릭 클래스에서 해당 메서드는 다음과 같은 특별한 규칙이 적용 됩니다.  
  
-   제네릭 클래스의 메서드는 매개 변수, 반환 형식 또는 로컬 변수 형식 매개 변수를 사용할 수 있습니다.  
  
-   제네릭 클래스의 메서드는 매개 변수, 반환 형식 또는 로컬 변수 개방형 이나 폐쇄형 생성된 형식을 사용할 수 있습니다.  
  
### 제네릭 클래스의 제네릭이 아닌 메서드  
 추가 형식 매개 변수가 있는 제네릭 클래스의 메서드는 바깥쪽 제네릭 클래스의 매개 변수가 암시적으로 되어 있지만 일반적으로 제네릭이 아닌 라고 합니다.  
  
 직접 또는 개방형 생성된 형식이 제네릭이 아닌 메서드의 시그니처와 바깥쪽 클래스의 하나 이상의 형식 매개 변수를 포함할 수 있습니다.  예를 들면 다음과 같습니다.  
  
 `void MyMethod(MyClass<ItemType> x) {}`  
  
 이러한 메서드의 본문에서 이러한 형식 매개 변수를 사용할 수도 있습니다.  
  
## 예제  
 다음 예제에서는 제네릭이 아닌 메서드 `ProtectData` 를 제네릭 클래스 `MyClass<ItemType>` 안에서 선언합니다.  메서드는 개방형 생성된 형식에서 해당 시그니처에게 클래스 형식 매개 변수 `ItemType`를 사용합니다.  
  
```  
// generics_non_generic_methods1.cpp  
// compile with: /clr  
// Non-generic methods within a generic class.  
using namespace System;  
  
generic <typename ItemType>  
ref class MyClass {  
public:  
   String^ name;  
   ItemType data;  
  
   MyClass(ItemType x) {  
      data = x;  
   }  
  
   // Non-generic method using the type parameter:  
   virtual void ProtectData(MyClass<ItemType>^ x) {  
      data = x->data;  
   }  
};  
  
// ItemType defined as String^  
ref class MyMainClass: MyClass<String^> {  
public:  
   // Passing "123.00" to the constructor:  
   MyMainClass(): MyClass<String^>("123.00") {  
      name = "Jeff Smith";   
   }   
  
   virtual void ProtectData(MyClass<String^>^ x) override {  
      x->data = String::Format("${0}**", x->data);  
   }  
  
   static void Main() {  
      MyMainClass^ x1 = gcnew MyMainClass();  
  
      x1->ProtectData(x1);  
      Console::WriteLine("Name: {0}", x1->name);  
      Console::WriteLine("Amount: {0}", x1->data);  
   }  
};  
  
int main() {  
   MyMainClass::Main();  
}  
```  
  
  **Name: Jeff Smith**  
**Amount: $123.00\*\***   
## 제네릭 클래스의 제네릭 메서드  
 제네릭과 비 제네릭 클래스에서 제너릭 메서드를 선언할 수 있습니다.  예를 들면 다음과 같습니다.  
  
## 예제  
  
```  
// generics_method2.cpp  
// compile with: /clr /c  
generic <typename Type1>  
ref class G {  
public:  
   // Generic method having a type parameter  
   // from the class, Type1, and its own type  
   // parameter, Type2  
   generic <typename Type2>  
   void Method1(Type1 t1, Type2 t2) { F(t1, t2); }  
  
   // Non-generic method:  
   // Can use the class type param, Type1, but not Type2.  
   void Method2(Type1 t1) { F(t1, t1); }  
  
   void F(Object^ o1, Object^ o2) {}  
};  
```  
  
 제네릭이 아닌 메서드는 여전히 클래스의 형식 매개 변수로 매개 변수화 되지만 추가 형식 매개 변수는 갖고 있지 않습니다.  
  
 제네릭 클래스의 모든 메서드 타입은 정적, 인스턴스 및 가상 메서드를 포함해서 제너릭이 될 수 있습니다.  
  
## 예제  
 다음 예제에서는 제네릭 클래스 내에서 제네릭 메서드를 사용하고 선언하는 것을 설명합니다.  
  
```  
// generics_generic_method2.cpp  
// compile with: /clr  
using namespace System;  
generic <class ItemType>  
ref class MyClass {  
public:  
   // Declare a generic method member.  
   generic <class Type1>  
   String^ MyMethod(ItemType item, Type1 t) {  
      return String::Concat(item->ToString(), t->ToString());  
   }  
};  
  
int main() {  
   // Create instances using different types.  
   MyClass<int>^ myObj1 = gcnew MyClass<int>();  
   MyClass<String^>^ myObj2 = gcnew MyClass<String^>();  
   MyClass<String^>^ myObj3 = gcnew MyClass<String^>();  
  
   // Calling MyMethod using two integers.  
   Console::WriteLine("MyMethod returned: {0}",  
            myObj1->MyMethod<int>(1, 2));  
  
   // Calling MyMethod using an integer and a string.  
   Console::WriteLine("MyMethod returned: {0}",  
            myObj2->MyMethod<int>("Hello #", 1));  
  
   // Calling MyMethod using two strings.  
   Console::WriteLine("MyMethod returned: {0}",  
       myObj3->MyMethod<String^>("Hello ", "World!"));  
  
   // generic methods can be called without specifying type arguments  
   myObj1->MyMethod<int>(1, 2);  
   myObj2->MyMethod<int>("Hello #", 1);  
   myObj3->MyMethod<String^>("Hello ", "World!");  
}  
```  
  
  **MyMethod 반환: 12**  
**MyMethod 반환: Hello \#1**  
**MyMethod 반환: Hello World\!**   
## 제네릭 클래스에서 중첩 된 형식을 사용  
 일반 클래스와 마찬가지로 제네릭 클래스 내부에 다른 형식을 선언할 수 있습니다.  중첩된 클래스 선언은 외부 클래스 선언의 형식 매개 변수에 의해 암시적으로 매개변수화 됩니다.  따라서 각 중첩 된 클래스는 생성된 각 외부 형식에 대해 정의 됩니다.  에를 들어 선언에서.  
  
```  
// generic_classes_5.cpp  
// compile with: /clr /c  
generic <typename ItemType>  
ref struct Outer {  
   ref class Inner {};  
};  
```  
  
 Outer\<int\>::Inner 형식은 Outer\<double\>::Inner 형식과 다릅니다.  
  
 제네릭 클래스의 제네릭 메서드의 경우와 마찬가지로 중첩된 형식에 대해 추가 형식 매개 변수를 정의할 수 있습니다.  형식 매개 변수 이름이 동일한 내부 및 외부 클래스를 사용 하면 내부 형식 매개 변수가 외부 형식 매개 변수가 숨겨집니다.  
  
```  
// generic_classes_6.cpp  
// compile with: /clr /c  
generic <typename ItemType>  
ref class Outer {  
   ItemType outer_item;   // refers to outer ItemType  
  
   generic <typename ItemType>  
   ref class Inner {  
      ItemType inner_item;   // refers to Inner ItemType  
   };  
};  
```  
  
 바깥쪽 형식 매개 변수를 참조할 수 없으므로 컴파일러는 이 상황에서 경고를 생성 합니다.  
  
 생성 된 중첩 된 제네릭 형식에 이름을 지정 하는 경우, 내부 형식이 바깥쪽 형식의 형식 매개 변수로 암시적으로 매개 변수화 되더라도, 바깥쪽 형식의 형식 매개 변수는 내부 형식에 대한 형식 매개 변수 목록에 포함 되지 않습니다.  위의 경우, 생성 된 형식의 이름은  Outer\<int\>::Inner\<string\> 입니다.  
  
 다음 예제는 제네릭 클래스에서 중첩 형식을 사용하여 연결된 목록을 읽고 빌드하는 방법을 설명합니다.  
  
## 예제  
  
```  
// generics_linked_list.cpp  
// compile with: /clr  
using namespace System;  
generic <class ItemType>  
ref class LinkedList {  
// The node class:  
public:  
   ref class Node {  
   // The link field:  
   public:  
      Node^ next;  
      // The data field:  
      ItemType item;   
   } ^first, ^current;  
};  
  
ref class ListBuilder {  
public:  
   void BuildIt(LinkedList<double>^ list) {  
      /* Build the list */  
      double m[5] = {0.1, 0.2, 0.3, 0.4, 0.5};  
      Console::WriteLine("Building the list:");  
  
      for (int n=0; n<=4; n++) {  
         // Create a new node:  
         list->current = gcnew LinkedList<double>::Node();  
  
         // Assign a value to the data field:  
         list->current->item = m[n];  
  
         // Set the link field "next" to be the same as   
         // the "first" field:  
         list->current->next = list->first;  
  
         // Redirect "first" to the new node:  
         list->first = list->current;  
  
         // Display node's data as it builds:  
         Console::WriteLine(list->current->item);  
      }  
   }  
  
   void ReadIt(LinkedList<double>^ list) {  
      // Read the list  
      // Make "first" the "current" link field:  
      list->current = list->first;  
      Console::WriteLine("Reading nodes:");  
  
      // Read nodes until current == null:  
      while (list->current != nullptr) {  
         // Display the node's data field:  
         Console::WriteLine(list->current->item);  
  
         // Move to the next node:  
         list->current = list->current->next;  
      }  
   }  
};  
  
int main() {  
   // Create a list:  
   LinkedList<double>^ aList = gcnew LinkedList<double>();  
  
   // Initialize first node:  
   aList->first = nullptr;  
  
   // Instantiate the class, build, and read the list:   
   ListBuilder^ myListBuilder = gcnew ListBuilder();  
   myListBuilder->BuildIt(aList);  
   myListBuilder->ReadIt(aList);  
}  
```  
  
  **목록 작성:**  
**0.1**  
**0.2**  
**0.3**  
**0.4**  
**0.5**  
**노드 읽기:**  
**0.5**  
**0.4**  
**0.3**  
**0.2**  
**0.1**   
## 제네릭 클래스의 속성, 이벤트, 인덱서 및 연산자  
  
-   속성, 이벤트, 인덱서 및 연산자는 `ItemType`가 클래스의 형식 매개변수 일 때, 반환 값, 매개 변수, 및 지역 변수로 제네릭 클래스를 포함하는 형식 매개 변수를 사용합니다.  
  
    ```  
    public ItemType MyProperty {}  
    ```  
  
-   속성, 이벤트, 인덱서 및 연산자는 자체 매개 변수화 될 수 없습니다.  
  
## 예제  
 이 예제에는 제네릭 클래스 내에서 인스턴스 속성의 선언을 보여 줍니다.  
  
```  
// generics_generic_properties1.cpp  
// compile with: /clr  
using namespace System;  
  
generic <typename ItemType>  
ref class MyClass {  
private:  
   property ItemType myField;  
  
public:  
   property ItemType MyProperty {  
      ItemType get() {  
         return myField;   
      }  
      void set(ItemType value) {  
         myField = value;  
      }  
   }  
};  
  
int main() {  
   MyClass<String^>^ c = gcnew MyClass<String^>();  
   MyClass<int>^ c1 = gcnew MyClass<int>();  
  
   c->MyProperty = "John";  
   c1->MyProperty = 234;  
  
   Console::Write("{0}, {1}", c->MyProperty, c1->MyProperty);  
}  
```  
  
  **John, 234**   
## 예제  
 다음 예제에서는 이벤트를 사용 하여 제네릭 클래스를 보여 줍니다.  
  
```  
// generics_generic_with_event.cpp  
// compile with: /clr  
// Declare a generic class with an event and  
// invoke events.  
using namespace System;  
  
// declare delegates  
generic <typename ItemType>  
delegate void ClickEventHandler(ItemType);  
  
// generic class that defines events  
generic <typename ItemType>  
ref class EventSource {  
public:  
   // declare the event OnClick  
   event ClickEventHandler<ItemType>^ OnClick;   
   void FireEvents(ItemType item) {  
      // raises events  
      OnClick(item);  
   }  
};  
  
// generic class that defines methods that will called when  
// event occurs  
generic <typename ItemType>  
ref class EventReceiver {  
public:  
   void OnMyClick(ItemType item) {  
     Console::WriteLine("OnClick: {0}", item);  
   }  
};  
  
int main() {  
   EventSource<String^>^ MyEventSourceString =  
                   gcnew EventSource<String^>();  
   EventSource<int>^ MyEventSourceInt = gcnew EventSource<int>();  
   EventReceiver<String^>^ MyEventReceiverString =  
                   gcnew EventReceiver<String^>();  
   EventReceiver<int>^ MyEventReceiverInt = gcnew EventReceiver<int>();  
  
   // hook handler to event  
   MyEventSourceString->OnClick += gcnew ClickEventHandler<String^>(  
       MyEventReceiverString, &EventReceiver<String^>::OnMyClick);  
   MyEventSourceInt->OnClick += gcnew ClickEventHandler<int>(  
             MyEventReceiverInt, &EventReceiver<int>::OnMyClick);  
  
   // invoke events  
   MyEventSourceString->FireEvents("Hello");  
   MyEventSourceInt->FireEvents(112);  
  
   // unhook handler to event  
   MyEventSourceString->OnClick -= gcnew ClickEventHandler<String^>(  
        MyEventReceiverString, &EventReceiver<String^>::OnMyClick);  
   MyEventSourceInt->OnClick -= gcnew ClickEventHandler<int>(  
        MyEventReceiverInt, &EventReceiver<int>::OnMyClick);  
}  
```  
  
## 제네릭 구조체  
 제네릭 구조체를 선언하고 이용하는 규칙은 Visual C\+\+ 언어 참조에서 설명한 차이점을 제외 하면 제네릭 클래스와 동일 합니다.  
  
## 예제  
 다음 예제에서는 필드 하나를 사용하여 제네릭 구조체, `MyGenStruct`, `myField`을 선언하고, 이 필드에 다양한 형식의 값 \(`int`, **double**, **String^**\)을 할당합니다.  
  
```  
// generics_generic_struct1.cpp  
// compile with: /clr  
using namespace System;  
  
generic <typename ItemType>  
ref struct MyGenStruct {  
public:  
   ItemType myField;  
  
   ItemType AssignValue(ItemType item) {  
      myField = item;  
      return myField;  
   }  
};  
  
int main() {  
   int myInt = 123;  
   MyGenStruct<int>^ myIntObj = gcnew MyGenStruct<int>();  
   myIntObj->AssignValue(myInt);  
   Console::WriteLine("The field is assigned the integer value: {0}",  
            myIntObj->myField);  
  
   double myDouble = 0.123;  
   MyGenStruct<double>^ myDoubleObj = gcnew MyGenStruct<double>();  
   myDoubleObj->AssignValue(myDouble);  
   Console::WriteLine("The field is assigned the double value: {0}",  
            myDoubleObj->myField);  
  
   String^ myString = "Hello Generics!";  
   MyGenStruct<String^>^ myStringObj = gcnew MyGenStruct<String^>();  
   myStringObj->AssignValue(myString);  
   Console::WriteLine("The field is assigned the string: {0}",  
            myStringObj->myField);  
}  
```  
  
  **정수 값 123이 필드에 할당 됩니다.**  
**더블 값 0.123이 필드에 할당 됩니다.**  
**문자열 Hello Generics\! 가 필드에 할당 됩니다.**   
## 참고 항목  
 [Generics](../windows/generics-cpp-component-extensions.md)