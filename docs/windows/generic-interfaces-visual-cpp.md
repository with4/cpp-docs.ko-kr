---
title: 제네릭 인터페이스 (Visual c + +) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- generic interfaces
- interfaces, generic [C++}
ms.assetid: f3da788a-ba83-4db7-9dcf-9b95a8fb9d1a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8e16a2ab8a1ee0c9255f394d033bda2a7afc2b7e
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
---
# <a name="generic-interfaces-visual-c"></a>제네릭 인터페이스(Visual C++)
클래스에 매개 변수를 형식에 적용 되는 제한 사항을 인터페이스에 형식 매개 변수를 적용 하는 것과 동일 (참조 [제네릭 클래스 (C + + /cli CLI)](../windows/generic-classes-cpp-cli.md)).  
  
 함수 오버 로드를 제어 하는 규칙이 제네릭 인터페이스 또는 제네릭 클래스 내의 기능에 대해 동일 합니다.  
  
 명시적 인터페이스 멤버 구현에서는 생성 된 인터페이스 형식에서 (다음 예제 참조)는 간단한 인터페이스 형식과 동일한 방식으로 작동 합니다.  
  
 인터페이스에 대 한 자세한 내용은 참조 하십시오. [인터페이스 클래스](../windows/interface-class-cpp-component-extensions.md)합니다.  
  
## <a name="syntax"></a>구문  
  
```  
[attributes] generic <class-key type-parameter-identifier[, ...]>  
[type-parameter-constraints-clauses][accesibility-modifiers] interface class identifier [: base-list] {   interface-body} [declarators] ;  
```  
  
## <a name="remarks"></a>설명  
 *특성* (선택 사항)  
 추가 선언 정보입니다. 특성 및 특성 클래스에 대한 자세한 내용은 특성을 참조하십시오.  
  
 *클래스 키*  
 **클래스** 또는 **typename**  
  
 `type-parameter-identifier(s)`  
 쉼표로 구분 된 식별자 목록입니다.  
  
 `type-parameter-constraints-clauses`  
 에 지정 된 형식을 취합니다 [제네릭 형식 매개 변수에 대 한 제약 조건 (C + + /cli CLI)](../windows/constraints-on-generic-type-parameters-cpp-cli.md)  
  
 *액세스 가능성 한정자* (선택 사항)  
 액세스 가능성 한정자 (예: **공개 / 개인**).  
  
 *identifier*  
 인터페이스 이름입니다.  
  
 *자료 목록* (선택 사항)  
 하나 이상의 명시적 기본 인터페이스 쉼표로 구분 하 여 포함 된 목록입니다.  
  
 *인터페이스 본문*  
 인터페이스 멤버를 선언 합니다.  
  
 *선언 자* (선택 사항)  
 이 형식에 기반 하 여 변수를 선언 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에는 선언 하 고 제네릭 인터페이스를 인스턴스화하는 방법을 보여 줍니다. 예제에서는 제네릭 인터페이스 `IList<ItemType>` 선언 됩니다. 다음 두 개의 제네릭 클래스에 의해 구현 되며 `List1<ItemType>` 및 `List2<ItemType>`, 다른 구현으로 합니다.  
  
```  
// generic_interface.cpp  
// compile with: /clr  
using namespace System;  
  
// An exception to be thrown by the List when  
// attempting to access elements beyond the  
// end of the list.  
ref class ElementNotFoundException : Exception {};  
  
// A generic List interface  
generic <typename ItemType>  
public interface class IList {  
   ItemType MoveFirst();  
   bool Add(ItemType item);  
   bool AtEnd();  
   ItemType Current();  
   void MoveNext();  
};  
  
// A linked list implementation of IList  
generic <typename ItemType>  
public ref class List1 : public IList<ItemType> {  
   ref class Node {  
      ItemType m_item;  
  
   public:  
      ItemType get_Item() { return m_item; };  
      void set_Item(ItemType value) { m_item = value; };  
  
      Node^ next;  
  
      Node(ItemType item) {  
         m_item = item;  
         next = nullptr;  
      }  
   };  
  
   Node^ first;  
   Node^ last;  
   Node^ current;  
  
   public:  
   List1() {  
      first = nullptr;  
      last = first;  
      current = first;  
   }  
  
   virtual ItemType MoveFirst() {  
      current = first;  
      if (first != nullptr)  
        return first->get_Item();  
      else  
         return ItemType();  
   }  
  
   virtual bool Add(ItemType item) {  
      if (last != nullptr) {   
         last->next = gcnew Node(item);  
         last = last->next;  
      }  
      else {  
         first = gcnew Node(item);  
         last = first;  
         current = first;  
      }  
      return true;  
   }  
  
   virtual bool AtEnd() {  
      if (current == nullptr )  
        return true;  
      else   
        return false;  
   }  
  
   virtual ItemType Current() {  
       if (current != nullptr)  
         return current->get_Item();  
       else  
         throw gcnew ElementNotFoundException();  
   }  
  
   virtual void MoveNext() {  
      if (current != nullptr)  
       current = current->next;  
      else  
        throw gcnew ElementNotFoundException();  
   }  
};  
  
// An array implementation of IList  
generic <typename ItemType>  
ref class List2 : public IList<ItemType> {  
   array<ItemType>^ item_array;  
   int count;  
   int current;  
  
   public:  
  
   List2() {  
      // not yet possible to declare an  
      // array of a generic type parameter  
      item_array = gcnew array<ItemType>(256);  
      count = current = 0;  
   }  
  
   virtual ItemType MoveFirst() {  
      current = 0;  
      return item_array[0];  
   }  
  
   virtual bool Add(ItemType item) {  
      if (count < 256)  
         item_array[count++] = item;  
      else  
        return false;  
      return true;  
   }  
  
   virtual bool AtEnd() {  
      if (current >= count)  
        return true;  
      else  
        return false;  
   }  
  
   virtual ItemType Current() {  
      if (current < count)  
        return item_array[current];  
      else  
        throw gcnew ElementNotFoundException();  
   }  
  
   virtual void MoveNext() {  
      if (current < count)   
         ++current;  
      else  
         throw gcnew ElementNotFoundException();  
   }  
};  
  
// Add elements to the list and display them.  
generic <typename ItemType>  
void AddStringsAndDisplay(IList<ItemType>^ list, ItemType item1, ItemType item2) {  
   list->Add(item1);  
   list->Add(item2);  
   for (list->MoveFirst(); ! list->AtEnd(); list->MoveNext())  
     Console::WriteLine(list->Current());  
}  
  
int main() {  
   // Instantiate both types of list.  
  
   List1<String^>^ list1 = gcnew List1<String^>();  
   List2<String^>^ list2 = gcnew List2<String^>();  
  
   // Use the linked list implementation of IList.  
   AddStringsAndDisplay<String^>(list1, "Linked List", "List1");  
  
   // Use the array implementation of the IList.  
   AddStringsAndDisplay<String^>(list2, "Array List", "List2");  
}  
```  
  
```Output  
Linked List  
List1  
Array List  
List2  
```  
  
## <a name="example"></a>예제  
 이 예제에서는 제네릭 인터페이스를 선언 `IMyGenIface`, 및 두 개의 제네릭이 아닌 인터페이스 `IMySpecializedInt` 및 `ImySpecializedString`을 특수화 하는 `IMyGenIface`합니다. 두 개의 특수 인터페이스는 다음 두 개의 클래스에서 구현 `MyIntClass` 및 `MyStringClass`합니다. 제네릭 인터페이스를 특수화할 제네릭 및 제네릭이 아닌 인터페이스를 인스턴스화하고 인터페이스에 명시적으로 구현 된 멤버를 호출 하는 방법을 보여 줍니다.  
  
```  
// generic_interface2.cpp  
// compile with: /clr  
// Specializing and implementing generic interfaces.  
using namespace System;  
  
generic <class ItemType>  
public interface class IMyGenIface {  
   void Initialize(ItemType f);  
};  
  
public interface class IMySpecializedInt: public IMyGenIface<int> {  
   void Display();  
};  
  
public interface class IMySpecializedString: public IMyGenIface<String^> {  
   void Display();  
};  
  
public ref class MyIntClass: public IMySpecializedInt {  
   int myField;  
  
public:   
   virtual void Initialize(int f) {  
      myField = f;  
   }  
  
   virtual void Display() {  
      Console::WriteLine("The integer field contains: {0}", myField);  
   }      
};  
  
public ref struct MyStringClass: IMySpecializedString {      
   String^ myField;  
  
public:  
   virtual void Initialize(String^ f) {  
      myField = f;  
    }  
  
   virtual void Display() {  
      Console::WriteLine("The String field contains: {0}", myField);  
   }  
};  
  
int main() {  
   // Instantiate the generic interface.  
   IMyGenIface<int>^ myIntObj = gcnew MyIntClass();  
  
   // Instantiate the specialized interface "IMySpecializedInt."  
   IMySpecializedInt^ mySpIntObj = (IMySpecializedInt^) myIntObj;  
  
   // Instantiate the generic interface.  
   IMyGenIface<String^>^ myStringObj = gcnew MyStringClass();  
  
   // Instantiate the specialized interface "IMySpecializedString."  
   IMySpecializedString^ mySpStringObj =   
            (IMySpecializedString^) myStringObj;  
  
   // Call the explicitly implemented interface members.  
   myIntObj->Initialize(1234);  
   mySpIntObj->Display();  
  
   myStringObj->Initialize("My string");  
   mySpStringObj->Display();  
}  
```  
  
```Output  
The integer field contains: 1234  
The String field contains: My string  
```  
  
## <a name="see-also"></a>참고 항목  
 [제네릭](../windows/generics-cpp-component-extensions.md)