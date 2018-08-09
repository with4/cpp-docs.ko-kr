---
title: 제네릭 클래스 (C + + /cli CLI) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- classes [C++], generic
- generic classes [C++], about generic classes
- data types [C++], generic
- generic classes
- generics [C++], declaring generic classes
ms.assetid: 0beb99e1-1ec4-4fee-9836-ce9657d67a3a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: deeb40e54c0324874d9c99a42a98e7e852394dc4
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39643191"
---
# <a name="generic-classes-ccli"></a>제네릭 클래스(C++/CLI)
제네릭 클래스는 다음 형식을 사용 하 여 선언 됩니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
[attributes]  
generic <class-key type-parameter-identifier(s)>  
[constraint-clauses]  
[accessibility-modifiers] ref class identifier  [modifiers]  
[: base-list]   
{  
class-body  
} [declarators] [;]  
```  
  
## <a name="remarks"></a>설명  
 위의 구문에서 다음과 같은 용어가 사용 됩니다.  
  
 *특성* (선택 사항)  
 추가 선언 정보입니다. 특성 및 특성 클래스에 대한 자세한 내용은 특성을 참조하십시오.  
  
 *클래스 키*  
 어느 **클래스** 또는 **typename**  
  
 *형식-매개 변수-식별자*,  
 형식 매개 변수의 이름을 지정 하는 식별자의 쉼표로 구분 된 목록입니다.  
  
 *제약 조건 절*  
 목록 (쉼표로 구분 되지 않습니다)의 **여기서** 절 형식 매개 변수 제약 조건을 지정 합니다. 형식을 사용 합니다.  
  
 `where`  *형식 매개 변수 식별자*`:`*제약 조건 목록*  `...`  
  
 *제약 조건 목록*  
 *클래스 또는 인터페이스*[`,` *...* ]  
  
 *액세스 가능성 한정자*  
 제네릭 클래스에 대 한 액세스 가능성 한정자입니다. 유일한 허용된 한정자는 Windows 런타임용 **개인**합니다. 한정자를 허용 되는 공용 언어 런타임 **사설** 하 고 **공용**.  
  
 *identifier*  
 제네릭 클래스는 모든 유효한 c + + 식별자의 이름입니다.  
  
 *한정자* (선택 사항)  
 한정자는 허용 **봉인** 하 고 **추상**합니다.  
  
 *기본-목록*  
 하나의 기본 클래스와 포함 된 목록을 쉼표로 구분 된 모든 인터페이스를 구현 합니다.  
  
 *클래스-본문*  
 필드, 멤버 함수 등을 포함 하는 클래스의 본문입니다.  
  
 *선언 자*  
 이 형식의 모든 변수를 선언 합니다. 예를 들어: `^` *식별자*[`,` ...]  
  
 같은 제네릭 클래스를 선언할 수 있습니다 (이때 키워드 **클래스** 대신 사용할 수 있습니다 **typename**). 이 예에서 `ItemType`, `KeyType` 및 `ValueType` 지점에서 지정 된 알 수 없는 유형이 위치 형식입니다. `HashTable<int, int>` 제네릭 형식의 생성 된 형식인 `HashTable<KeyType, ValueType>`합니다. 단일 제네릭 형식에서 생성 된 다른 형식의 숫자를 생성할 수 있습니다. 생성 된 형식 제네릭 클래스에서 생성 된 다른 ref 클래스 형식 처럼 처리 됩니다.  
  
```cpp  
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
  
 둘 다 값 형식 (같은 기본 제공 형식 **int** 또는 **double**, 또는 사용자 정의 값 형식) 하며 참조 형식을 제네릭 형식 인수로 사용할 수 있습니다. 제네릭 정의 내에서 구문은 관계 없이 동일 합니다. 구문적으로 알 수 없는 형식 참조 형식인 것 처럼 처리 됩니다. 그러나 런타임에서 실제로 사용 되는 형식이 값 형식인 경우 확인 하 고 멤버에 직접 액세스 하기 위해 생성된 된 적절 한 코드를 대체할 수 있습니다. 값 형식을 제네릭 형식 인수를 받았던 boxed 없습니다 및 따라서 boxing와 관련 된 성능 저하를 발생 하지 않습니다. 제네릭의 본문 내에서 사용 된 구문 이어야 합니다 `T^` 하 고 `->` 대신 `.`합니다. 사용할 때 [ref new, gcnew](../windows/ref-new-gcnew-cpp-component-extensions.md) 유형에 대 한 매개 변수가 적절 하 게 해석 됩니다 런타임에서 간단한 값 형식 만들기 형식 인수가 값 형식입니다.  
  
 제네릭 클래스를 선언할 수도 있습니다 [제네릭 형식 매개 변수에 대 한 제약 조건 (C + + CLI)](../windows/constraints-on-generic-type-parameters-cpp-cli.md) 형식 매개 변수에 사용할 수 있는 형식입니다. 다음 예제에서는 모든 형식에 대 한 사용 `ItemType` 구현 해야 합니다는 `IItem` 인터페이스입니다. 사용 하려고 **int**, 예를 들어는 구현 하지 않는 `IItem`, 형식 인수 제약 조건을 만족 하지 않는 때문에 컴파일 타임 오류가 생성 됩니다.  
  
```cpp  
// generic_classes_2.cpp  
// compile with: /clr /c  
interface class IItem {};  
generic <class ItemType>  
where ItemType : IItem  
ref class Stack {};  
```  
  
 동일한 네임 스페이스에서 제네릭 클래스 또는 형식 매개 변수 유형의 변경 하 여 오버 로드할 수 없습니다. 그러나 각 클래스는 다른 네임 스페이스에 있는, 경우 이러한 오버 로드할 수 있습니다. 예를 들어, 다음 두 클래스는 것이 좋습니다 `MyClass` 하 고 `MyClass<ItemType>`, 네임 스페이스의 `A` 및 `B`합니다. 두 클래스 c: 세 번째 네임 스페이스에 오버 로드할 수 있습니다.  
  
```cpp  
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
  
 기본 클래스 및 기본 인터페이스를 형식 매개 변수 수 없습니다. 그러나 기본 클래스는 다음과 같은 경우와 같이 인수로 형식 매개 변수를 포함할 수 있습니다.  
  
```cpp  
// generic_classes_4.cpp  
// compile with: /clr /c  
generic <typename ItemType>  
interface class IInterface {};  
  
generic <typename ItemType>  
ref class MyClass : IInterface<ItemType> {};  
```  
  
 생성자 및 소멸자는 한 번 각 개체 인스턴스에 대 한 (정상적으로 실행). 정적 생성자는 생성 된 각 형식에 대 한 한 번 실행 됩니다.  
  
## <a name="fields-in-generic-classes"></a>제네릭 클래스의 필드  
 이 섹션에서는 제네릭 클래스의 정적 필드 및 인스턴스의 사용을 보여 줍니다.  
  
### <a name="instance-variables"></a>인스턴스 변수  
 제네릭 클래스의 인스턴스 변수 형식 및 바깥쪽 클래스의 모든 형식 매개 변수를 포함 하는 변수 이니셜라이저를 가질 수 있습니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 세 가지 다른 인스턴스의 제네릭 클래스인 MyClass\<ItemType >, 적절 한 형식 인수를 사용 하 여 생성 됩니다 (**int**, **double**, 및 **문자열**).  
  
```cpp  
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
  
```Output  
Integer field = 123  
Double field = 1.23  
String field = ABC  
```  
  
## <a name="static-variables"></a>정적 변수  
 새 제네릭 형식 생성에 모든 정적 변수가의 새 인스턴스를 만들 하 고 해당 형식에 대 한 정적 생성자 실행 됩니다.  
  
 정적 변수는 바깥쪽 클래스의 모든 형식 매개 변수를 사용할 수 있습니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 정적 필드 및 제네릭 클래스 내에서 정적 생성자를 사용 하는 방법을 보여 줍니다.  
  
```cpp  
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
  
```Output  
Static constructor called.  
Static constructor called.  
Static constructor called.  
Test1  
```  
  
## <a name="methods-in-generic-classes"></a>제네릭 클래스의 메서드  
 제네릭 클래스의 메서드는 제네릭이 될 수 있습니다, 제네릭이 아닌 메서드는 클래스 형식 매개 변수로 암시적으로 매개 변수화 됩니다.  
  
 제네릭 클래스 내의 메서드에 다음과 같은 특별 한 규칙이 적용 됩니다.  
  
-   제네릭 클래스의 메서드 매개 변수, 반환 형식 또는 로컬 변수 형식 매개 변수에 사용할 수 있습니다.  
  
-   제네릭 클래스의 메서드 매개 변수, 반환 형식 또는 지역 변수 열림 또는 닫힘 생성 된 형식을 사용할 수 있습니다.  
  
### <a name="non-generic-methods-in-generic-classes"></a>제네릭 클래스의 제네릭이 아닌 메서드  
 추가 형식 매개 변수가 없는 제네릭 클래스의 메서드는 암시적으로 바깥쪽 제네릭 클래스에 의해 매개 변수화 됩니다 있지만 일반적으로 비 제네릭 라고 합니다.  
  
 직접 또는 개방형 생성된 형식에서 비 제네릭 메서드의 시그니처와 바깥쪽 클래스의 하나 이상의 형식 매개 변수를 포함할 수 있습니다. 예를 들어:  
  
 `void MyMethod(MyClass<ItemType> x) {}`  
  
 이러한 메서드의 본문에서 이러한 형식 매개 변수를 사용할 수도 있습니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 비 제네릭 메서드를 선언 `ProtectData`에 제네릭 클래스 내의 `MyClass<ItemType>`합니다. 클래스 형식 매개 변수를 사용 하는 메서드 `ItemType` 시그니처에 개방형 생성된 형식에서입니다.  
  
```cpp  
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
  
```Output  
Name: Jeff Smith  
Amount: $123.00**  
```  
  
## <a name="generic-methods-in-generic-classes"></a>제네릭 클래스의 제네릭 메서드  
 제네릭 및 제네릭이 아닌 클래스의 제네릭 메서드를 선언할 수 있습니다. 예를 들어:  
  
## <a name="example"></a>예  
  
```cpp  
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
  
 제네릭이 아닌 메서드는 클래스의 형식 매개 변수로 매개 변수화 된 되었지만 추가 형식 매개 변수가 없는 점에서 일반 계속 됩니다.  
  
 모든 유형의 제네릭 클래스의 메서드는 제네릭를 포함 하 여 정적, 인스턴스 및 가상 메서드 수 있습니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 선언 하 고 제네릭 클래스 내에서 제네릭 메서드를 사용 하 여 보여 줍니다.  
  
```cpp  
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
  
```Output  
MyMethod returned: 12  
MyMethod returned: Hello #1  
MyMethod returned: Hello World!  
```  
  
## <a name="using-nested-types-in-generic-classes"></a>제네릭 클래스에서 중첩 된 형식 사용  
 일반 클래스와 마찬가지로 제네릭 클래스 내에서 다른 형식을 선언할 수 있습니다. 중첩된 클래스 선언 외부 클래스 선언의 형식 매개 변수로 매개 변수화 암시적으로 됩니다. 따라서 중첩 된 클래스는 생성 된 각 외부 형식에 대 한 정의 됩니다. 예를 들어 선언에서  
  
```cpp  
// generic_classes_5.cpp  
// compile with: /clr /c  
generic <typename ItemType>  
ref struct Outer {  
   ref class Inner {};  
};  
```  
  
 형식 `Outer<int>::Inner` 형식으로 같지 않습니다 `Outer<double>::Inner`합니다.  
  
 제네릭 클래스에서 제네릭 메서드의 경우와 마찬가지로 중첩 된 형식에 대 한 추가 형식 매개 변수를 정의할 수 있습니다. 내부 및 외부 클래스에서 형식 매개 변수 이름과 사용 하는 경우 내부 형식 매개 변수가 외부 형식 매개 변수가 숨겨집니다.  
  
```cpp  
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
  
 외부 형식 매개 변수를 참조할 수 없으므로 이므로 컴파일러는이 상황에서 경고를 생성 합니다.  
  
 생성 된 중첩 된 제네릭 형식을 명명 하는 경우 내부 형식을 외부 형식의 형식 매개 변수에 의해 암시적으로 매개 변수화 된 경우에 외부 형식의 형식 매개 변수는 내부 형식에 대 한 형식 매개 변수 목록에 포함 되지 않습니다. 위의 예에서 생성 된 형식의 이름을 것 `Outer<int>::Inner<string>`입니다.  
  
 다음 예제에서는 제네릭 클래스에서 중첩 된 형식을 사용 하 여 연결된 된 목록을 읽고 빌드를 보여 줍니다.  
  
## <a name="example"></a>예  
  
```cpp  
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
  
```Output  
Building the list:  
0.1  
0.2  
0.3  
0.4  
0.5  
Reading nodes:  
0.5  
0.4  
0.3  
0.2  
0.1  
```  
  
## <a name="properties-events-indexers-and-operators-in-generic-classes"></a>속성, 이벤트, 인덱서 및 제네릭 클래스의 연산자  
  
-   속성, 이벤트, 인덱서 및 연산자 반환 값, 매개 변수 또는 지역 변수인 경우와 같이 바깥쪽 제네릭 클래스의 형식 매개 변수를 사용할 수 `ItemType` 클래스의 형식 매개 변수입니다.  
  
    ```cpp  
    public ItemType MyProperty {}  
    ```  
  
-   속성, 이벤트, 인덱서 및 연산자 자체 수 매개 변수화 수 없습니다.  
  
## <a name="example"></a>예  
 이 예제에서는 제네릭 클래스 내의 인스턴스 속성의 선언을 보여 줍니다.  
  
```cpp  
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
  
```Output  
John, 234  
```  
  
## <a name="example"></a>예  
 다음 예제에서는 이벤트를 사용 하 여 제네릭 클래스를 보여 줍니다.  
  
```cpp  
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
  
## <a name="generic-structs"></a>제네릭 구조체  
 규칙을 선언 하 고 제네릭 구조체를 사용 하 여 Visual c + + 언어 참조에서에 명시 된 차이점을 제외 하면 제네릭 클래스와 동일 합니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 제네릭 구조체를 선언 `MyGenStruct`, 단일 필드를 갖는 `myField`, 다양 한 형식의 값을 할당 하 고 (**int**를 **double**, `String^`)이이 필드에 합니다.  
  
```cpp  
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
  
```Output  
The field is assigned the integer value: 123  
The field is assigned the double value: 0.123  
The field is assigned the string: Hello Generics!  
```  
  
## <a name="see-also"></a>참고 항목  
 [제네릭](../windows/generics-cpp-component-extensions.md)