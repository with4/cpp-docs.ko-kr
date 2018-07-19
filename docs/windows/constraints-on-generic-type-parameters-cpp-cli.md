---
title: 제네릭에 대 한 제약 조건 형식 매개 변수 (C + + /cli CLI) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- where
dev_langs:
- C++
helpviewer_keywords:
- where keyword [C++]
- constraints, C++
ms.assetid: eb828cc9-684f-48a3-a898-b327700c0a63
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c9787eb87ab701d067762a436d92b2fba3fabcbb
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33883344"
---
# <a name="constraints-on-generic-type-parameters-ccli"></a>제네릭 형식 매개 변수에 대한 제약 조건(C++/CLI)
제네릭 형식 또는 메서드 선언에는 제약 조건이 있는 형식 매개 변수를 한정할 수 있습니다. 제약 조건은 형식 인수로 사용되는 형식이 충족해야 하는 요구 사항입니다. 예를 들어, 형식 인수가 특정 인터페이스를 구현하거나 특정 클래스에서 상속해야 제한할 수 있습니다.  
  
 제약 조건은 선택적입니다. 매개 변수에 제약 조건을 지정하지 않는 것은 해당 매개 변수를 <xref:System.Object>로 제한하는 것과 동일합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
where type-parameter: constraint list  
```  
  
#### <a name="parameters"></a>매개 변수  
 *형식 매개 변수*  
 제한되는 형식 매개 변수 중 하나입니다.  
  
 *제약 조건 목록*  
 *제약 조건 목록* 제약 조건 사양의 쉼표로 구분 된 목록입니다. 이 목록은 형식 매개 변수로 구현해야 하는 인터페이스를 포함할 수 있습니다.  
  
 이 목록은 클래스를 포함할 수도 있습니다. 형식 인수가 기본 클래스 제약 조건을 만족하려면 제약 조건과 같은 클래스이거나 제약 조건에서 파생되어야 합니다.  
  
 `gcnew()`를 지정하여 형식 인수에 매개 변수가 없는 public 생성자가 있다는 것을 나타내거나, `ref class`를 지정하여 형식 인수가 클래스, 인터페이스, 대리자 또는 배열 형식이 포함된 참조 형식이어야 한다는 것을 나타내거나, `value class`를 지정하여 형식 인수가 값 형식이어야 한다는 것을 나타냅니다. Nullable 제외한 임의의 값 형식을\<T >를 지정할 수 있습니다.  
  
 제네릭 매개 변수를 제약 조건으로 지정할 수도 있습니다. 제한된 형식에 대해 제공되는 형식 인수는 제약 조건의 형식이거나 제약 조건의 형식에서 파생되어야 합니다. 이를 naked 형식 제약 조건이라고 합니다.  
  
## <a name="remarks"></a>설명  
 제약 조건 절 이루어져 **여기서** , 형식 매개 변수, 콜론 (**:**), 및 제약 조건 형식 매개 변수에 제한의 특성을 지정 합니다. **여기서** 상황에 맞는 키워드; 참조 [상황에 맞는 키워드](../windows/context-sensitive-keywords-cpp-component-extensions.md) 자세한 정보에 대 한 합니다. 여러 구분 **여기서** 공백으로 절.  
  
 제약 조건은 제네릭 형식 또는 메서드의 인수로 사용할 수 있는 형식에 대한 제한을 배치하기 위해 형식 매개 변수에 적용됩니다.  
  
 클래스 및 인터페이스 제약 조건은 인수 형식이 지정된 클래스이거나 지정된 클래스에서 상속되거나 지정된 인터페이스를 구현해야 함을 지정합니다.  
  
 제네릭 형식 또는 메서드에 제약 조건을 적용하면 해당 형식 또는 메서드의 코드에서 제약 조건이 있는 형식의 알려진 기능을 사용할 수 있습니다. 예를 들어, 형식 매개 변수를 구현 하는 제네릭 클래스 선언할 수 있습니다는 **IComparable\<T >** 인터페이스:  
  
```  
// generics_constraints_1.cpp  
// compile with: /c /clr  
using namespace System;  
generic <typename T>  
where T : IComparable<T>  
ref class List {};  
```  
  
 이 제약 조건은 형식 인수에 사용 해야 `T` 구현 `IComparable<T>` 컴파일 타임에 있습니다. 또한 있습니다 인터페이스 메서드를 같은 **CompareTo**가 호출 됩니다. 인터페이스 메서드를 호출하기 위해 형식 매개 변수의 인스턴스를 캐스팅할 필요가 없습니다.  
  
 형식 인수의 클래스의 정적 메서드는 형식 매개 변수를 통해 호출할 수 없고, 실제 명명된 형식을 통해서만 호출할 수 있습니다.  
  
 제약 조건와 같은 기본 제공 형식을 포함 하는 값 형식 안 `int` 또는 **double**합니다. 값 형식은 파생된 클래스를 가질 수 없기 때문에, 하나의 클래스만 제약 조건을 만족할 수 있을 것입니다. 이러한 경우에 해당 제네릭을 특정 값 형식으로 대체한 형식 매개 변수를 사용하여 다시 작성할 수 있습니다.  
  
 제약 조건은 알 수 없는 형식이 메서드나 인터페이스를 지원함을 나타내지 않을 경우 컴파일러에서 메서드나 알 수 없는 형식의 다른 기능을 사용할 수 없으므로 일부 경우에 있어 필요합니다.  
  
 동일한 형식 매개 변수에 대한 여러 제약 조건은 쉼표로 구분된 목록에 지정할 수 있습니다.  
  
```  
// generics_constraints_2.cpp  
// compile with: /c /clr  
using namespace System;  
using namespace System::Collections::Generic;  
generic <typename T>  
where T : List<T>, IComparable<T>  
ref class List {};  
```  
  
 여러 개의 형식 매개 변수를 사용 하 여 하나 **여기서** 각 형식 매개 변수에 대 한 절. 예를 들어:  
  
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
  
 요약하면, 다음 규칙에 따라 코드에서 제약 조건을 사용합니다.  
  
-   여러 제약 조건이 나열될 경우 순서에 상관없이 표시될 수 있습니다.  
  
-   제약 조건은 추상 기본 클래스와 같은 클래스 형식일 수도 있습니다. 그러나 제약 조건은 값 형식 또는 sealed 클래스일 수 없습니다.  
  
-   제약 조건 자체가 형식 매개 변수가 될 수 없지만, 개방형 생성 형식에 형식 매개 변수를 포함할 수 있습니다. 예를 들어:  
  
    ```  
    // generics_constraints_4.cpp  
    // compile with: /c /clr  
    generic <typename T>  
    ref class G1 {};  
  
    generic <typename Type1, typename Type2>  
    where Type1 : G1<Type2>   // OK, G1 takes one type parameter  
    ref class G2{};  
    ```  
  
## <a name="example"></a>예제  
 다음 예제에서는 제약 조건을 사용하여 형식 매개 변수에서 인스턴스 메서드를 호출하는 방법을 보여 줍니다.  
  
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
  
```Output  
"parent" is not a senior  
"grandfather" is a senior  
```  
  
## <a name="example"></a>예제  
 제네릭 형식 매개 변수를 제약 조건으로 사용하면 naked 형식 제약이라고 합니다. 고유한 형식 매개 변수가 있는 멤버 함수가 포함 형식의 형식 매개 변수에 해당 매개 변수를 제한할 필요가 있을 때 naked 형식 제약 조건이 유용합니다.  
  
 다음 예제에서 T는 Add 메서드의 컨텍스트에서 naked 형식 제약 조건입니다.  
  
 naked 형식 제약 조건은 제네릭 클래스 정의에서 사용할 수도 있습니다. 컴파일러에서는 naked 형식 제약 조건이 <xref:System.Object>에서 파생된다는 점을 제외하고는 이 제약 조건에 대해 어떠한 정보도 알 수 없으므로 제네릭 클래스가 있는 naked 형식 제약 조건의 유용성에는 한계가 있습니다. 두 형식 매개 변수 사이의 상속 관계를 적용하려는 시나리오에서 제네릭 클래스에 naked 형식 제약 조건을 사용합니다.  
  
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
  
## <a name="see-also"></a>참고 항목  
 [제네릭](../windows/generics-cpp-component-extensions.md)