---
title: 제네릭 대리자 (Visual c + +) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- generic delegates
- delegates, generic [C++]
ms.assetid: 09d430b2-1aef-4fbc-87f9-9d7b8185d798
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5aa0bc804b3308a9b77c93cf40a2ba9cab7558a8
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39652911"
---
# <a name="generic-delegates-visual-c"></a>제네릭 대리자(Visual C++)
대리자에 제네릭 형식 매개 변수를 사용할 수 있습니다. 대리자에 대 한 자세한 내용은 참조 하세요. [delegate (c + + 구성 요소 확장)](../windows/delegate-cpp-component-extensions.md)합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
[attributes]   
generic < [class | typename] type-parameter-identifiers>  
[type-parameter-constraints-clauses]  
[accessibility-modifiers] delegate result-type identifier   
([formal-parameters]);  
```  
  
### <a name="parameters"></a>매개 변수  
 *특성* (선택 사항)  
 추가 선언 정보입니다. 특성 및 특성 클래스에 대한 자세한 내용은 특성을 참조하십시오.  
  
 *type-parameter-identifier(s)*  
 형식 매개 변수에 대한 식별자의 쉼표로 구분된 목록입니다.  
  
 *형식 매개 변수-제약 조건 절*  
 에 지정 된 형식은 [제네릭 형식 매개 변수에 대 한 제약 조건 (C + + /cli CLI)](../windows/constraints-on-generic-type-parameters-cpp-cli.md)  
  
 *액세스 가능성 한정자* (선택 사항)  
 액세스 가능성 한정자 (예: **공용**하십시오 **개인**).  
  
 *result-type*  
 대리자의 반환 형식입니다.  
  
 *identifier*  
 대리자의 이름입니다.  
  
 *정식 매개 변수* (선택 사항)  
 대리자의 매개 변수 목록입니다.  
  
## <a name="example"></a>예  
 대리자 형식 매개 변수는 대리자 개체가 만들어진 위치에 지정됩니다. 대리자 및 연결된 메서드의 시그니처는 둘 다 같아야 합니다. 다음 예제는 제네릭 대리자 선언을 보여 줍니다.  
  
```cpp  
// generics_generic_delegate1.cpp  
// compile with: /clr /c  
generic <class ItemType>  
delegate ItemType GenDelegate(ItemType p1, ItemType% p2);  
```  
  
## <a name="example"></a>예  
 다음 샘플은 다음을 보여 줍니다.  
  
-   서로 다른 생성된 형식에 동일한 대리자 개체를 사용할 수 없습니다. 형식마다 다른 대리자 개체를 만듭니다.  
  
-   제네릭 대리자를 제네릭 메서드에 연결할 수 있습니다.  
  
-   형식 인수를 지정하지 않고 제네릭 메서드를 호출하면 컴파일러는 호출에 대한 형식 인수를 유추하려고 합니다.  
  
```cpp  
// generics_generic_delegate2.cpp  
// compile with: /clr  
generic <class ItemType>  
delegate ItemType GenDelegate(ItemType p1, ItemType% p2);  
  
generic <class ItemType>  
ref struct MyGenClass {  
   ItemType MyMethod(ItemType i, ItemType % j) {  
      return ItemType();  
   }  
};  
  
ref struct MyClass {  
   generic <class ItemType>  
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
  
## <a name="example"></a>예  
 다음 예제에서는 제네릭 대리자 `GenDelegate<ItemType>`를 선언한 다음, `MyMethod` 형식 매개 변수를 사용하는 `ItemType` 메서드를 연결하여 인스턴스화합니다. 대리자의 두 인스턴스(정수 및 double)를 만들고 호출합니다.  
  
```cpp  
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
  
```Output  
Invoking the integer delegate: i = 123, j = 123  
Invoking the double delegate: m = 0.123, n = 0.123  
```  
  
## <a name="see-also"></a>참고 항목  
 [제네릭](../windows/generics-cpp-component-extensions.md)