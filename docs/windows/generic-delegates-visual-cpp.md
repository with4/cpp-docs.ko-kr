---
title: "Generic Delegates (Visual C++) | Microsoft Docs"
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
  - "generic delegates"
  - "delegates, generic [C++]"
ms.assetid: 09d430b2-1aef-4fbc-87f9-9d7b8185d798
caps.latest.revision: 20
caps.handback.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Generic Delegates (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

대리자가 있는 제네릭 형식 매개 변수를 사용할 수 있습니다.  대리자에 대한 자세한 내용은 다음을 참조하십시오. [delegate](../windows/delegate-cpp-component-extensions.md).  
  
## 구문  
  
```  
[attributes]   
generic < [class | typename] type-parameter-identifiers >  
[type-parameter-constraints-clauses]  
[accessibility-modifiers] delegate result-type identifier   
([formal-parameters]);  
```  
  
#### 매개 변수  
 `attributes`\(옵션\)  
 추가 선언 정보입니다.  특성 및 특성 클래스에 대한 자세한 내용은 특성을 참조 하십시오.  
  
 *형식\-매개 변수\-식별자*  
 형식 매개 변수 식별자의 쉼표로 구분 된 목록입니다.  
  
 `type-parameter-constraints-clauses`  
 [Constraints on Generic Type Parameters \(C\+\+\/CLI\)](../windows/constraints-on-generic-type-parameters-cpp-cli.md) 에 지정된 형식을 가져옵니다.  
  
 *액세스 가능성\-한정자* \(선택 사항\)  
 액세스 가능성 한정자 \(예:  **공용**, `private`\).  
  
 *결과\-형식*  
 대리자의 반환 형식입니다.  
  
 *identifier*  
 대리자 이름입니다.  
  
 *형식\-매개변수* \(선택 사항\)  
 대리자의 매개 변수 목록.  
  
## 예제  
 대리자 형식 매개 변수는 대리자 개체가 만들어진 위치에 지정 됩니다.  대리자와 연결된 메서드는 동일한 서명이 있어야 합니다.  다음 예제는 이벤트 대리자 선언의 예 입니다.  
  
```  
// generics_generic_delegate1.cpp  
// compile with: /clr /c  
generic < class ItemType>  
delegate ItemType GenDelegate(ItemType p1, ItemType% p2);  
```  
  
## 예제  
 다음 예제에서는 다음을 보여 줍니다.  
  
-   다른 구성된 형식을 사용 하여 동일한 대리자 개체를 사용할 수 없습니다.  형식 마다 다른 대리자 개체를 만듭니다.  
  
-   제네릭 대리자를 제네릭 메서드에 연결할 수 있습니다.  
  
-   제네릭 메서드의 형식 인수를 지정 하지 않고 호출 되면, 컴파일러는 호출에 대한 형식 인수를 유추 하려고 합니다.  
  
```  
// generics_generic_delegate2.cpp  
// compile with: /clr  
generic < class ItemType>  
delegate ItemType GenDelegate(ItemType p1, ItemType% p2);  
  
generic < class ItemType>  
ref struct MyGenClass {  
   ItemType MyMethod(ItemType i, ItemType % j) {  
      return ItemType();  
   }  
};  
  
ref struct MyClass {  
   generic < class ItemType>  
   static ItemType MyStaticMethod(ItemType i, ItemType % j) {  
      return ItemType();  
   }  
};  
  
int main() {  
   MyGenClass<int> ^ myObj1 = gcnew MyGenClass<int>();  
   MyGenClass<double> ^ myObj2 = gcnew MyGenClass<double>();  
   GenDelegate<int>^ myDelegate1 =  
      gcnew GenDelegate<int>(myObj1, &MyGenClass<int>::MyMethod);  
  
   GenDelegate<double>^ myDelegate2 =   
      gcnew GenDelegate<double>(myObj2, &MyGenClass<double>::MyMethod);  
  
   GenDelegate<int>^ myDelegate =  
      gcnew GenDelegate<int>(&MyClass::MyStaticMethod<int>);  
}  
```  
  
## 예제  
 다음 예제에서는 제네릭 대리자`GenDelegate<ItemType>`를 선언한 다음, `ItemType` 형식 매개 변수를 사용 하여 `MyMethod` 메서드를 연결하여 인스턴스화 합니다.  \(정수 및 double\) 대리자의 인스턴스 두 개를 만들고 호출 합니다.  
  
```  
// generics_generic_delegate.cpp  
// compile with: /clr  
using namespace System;  
  
// declare generic delegate  
generic <typename ItemType>  
delegate ItemType GenDelegate (ItemType p1, ItemType% p2);  
  
// Declare a generic class:  
generic <typename ItemType>  
ref class MyGenClass {  
public:  
   ItemType MyMethod(ItemType p1, ItemType% p2) {  
      p2 = p1;  
      return p1;  
    }  
};  
  
int main() {  
   int i = 0, j = 0;   
   double m = 0.0, n = 0.0;  
  
   MyGenClass<int>^ myObj1 = gcnew MyGenClass<int>();  
   MyGenClass<double>^ myObj2 = gcnew MyGenClass<double>();   
  
   // Instantiate a delegate using int.  
   GenDelegate<int>^ MyDelegate1 =   
      gcnew GenDelegate<int>(myObj1, &MyGenClass<int>::MyMethod);  
  
   // Invoke the integer delegate using MyMethod.  
   i = MyDelegate1(123, j);  
  
   Console::WriteLine(  
      "Invoking the integer delegate: i = {0}, j = {1}", i, j);  
  
   // Instantiate a delegate using double.  
   GenDelegate<double>^ MyDelegate2 =   
      gcnew GenDelegate<double>(myObj2, &MyGenClass<double>::MyMethod);  
  
   // Invoke the integer delegate using MyMethod.  
   m = MyDelegate2(0.123, n);  
  
   Console::WriteLine(  
      "Invoking the double delegate: m = {0}, n = {1}", m, n);  
}  
```  
  
  **정수 대리자 호출: i \= 123, j \= 123**  
**더블 대리자 호출: m \= 0.123, n \= 0.123**   
## 참고 항목  
 [Generics](../windows/generics-cpp-component-extensions.md)