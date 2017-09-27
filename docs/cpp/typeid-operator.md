---
title: "typeid 연산자 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- typeid operator
ms.assetid: 8871cee6-d6b9-4301-a5cb-bf3dc9798d61
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 3b987f26e7908c85ca1630059eec434c009c3ef4
ms.contentlocale: ko-kr
ms.lasthandoff: 09/25/2017

---
# <a name="typeid-operator"></a>typeid 연산자
## <a name="syntax"></a>구문  
  
```  
  
      typeid(   
      type-id  
       )  
typeid( expression )  
```  
  
## <a name="remarks"></a>설명  
 `typeid` 연산자를 사용하면 런타임에 개체 형식이 결정됩니다.  
  
 결과 `typeid` 는 **const type_info &**합니다. 값이에 대 한 참조는 **type_info** 나타내는 개체는 *유형 id* 또는 변수의 *식*형태에 따라 `typeid` 사용 . 참조 [type_info 클래스](../cpp/type-info-class.md) 자세한 정보에 대 한 합니다.  
  
 `typeid` 연산자 (추상 선언 자 또는 인스턴스)의 관리 되는 형식에서 작동 하지 않습니다, 참조 [typeid](../windows/typeid-cpp-component-extensions.md) 가져오기에 대 한 내용은 <xref:System.Type> 지정 된 형식의 합니다.  
  
 `typeid` 연산자는 다형 클래스 형식의 l-value에 적용될 때 런타임 검사를 하지 않습니다. 제공된 정적 정보로 개체의 true 형식을 확인할 수 없습니다. 다음과 같은 경우가 여기에 해당합니다.  
  
-   클래스에 대한 참조  
  
-   *로 역참조되는 포인터  
  
-   첨자 포인터(예: [ ]). 일반적으로 다형 형식의 포인터에 첨자를 사용하는 것은 안전하지 않습니다.  
  
 경우는 *식* 아직 해당 기본 클래스에서 파생 된 형식의 개체가 실제로 기본 클래스 유형 가리키는 **type_info** 파생된 클래스는 결과 대 한 참조입니다. *식* 다형 형식 (가상 함수가 있는 클래스)를 가리켜야 합니다. 그렇지 않으면 결과는 **type_info** 에서 참조 하는 정적 클래스는 *식*합니다. 또한 가리키는 개체를 사용하도록 포인터를 역참조해야 합니다. 결과 포인터를 역참조 하지 않으면 됩니다는 **type_info** 아니라를 가리키는 포인터에 대 한 합니다. 예:  
  
```  
// expre_typeid_Operator.cpp  
// compile with: /GR /EHsc  
#include <iostream>  
#include <typeinfo.h>  
  
class Base {  
public:  
   virtual void vvfunc() {}  
};  
  
class Derived : public Base {};  
  
using namespace std;  
int main() {  
   Derived* pd = new Derived;  
   Base* pb = pd;  
   cout << typeid( pb ).name() << endl;   //prints "class Base *"  
   cout << typeid( *pb ).name() << endl;   //prints "class Derived"  
   cout << typeid( pd ).name() << endl;   //prints "class Derived *"  
   cout << typeid( *pd ).name() << endl;   //prints "class Derived"  
   delete pd;  
}  
```  
  
 경우는 *식* 는 포인터를 역참조 하는 포인터 값이 0, **typeid** throw 한 [bad_typeid 예외](../cpp/bad-typeid-exception.md)합니다. 포인터가 유효한 개체를 가리키지 않을 경우는 `__non_rtti_object` 예외가 오류를 트리거한 RTTI를 분석 하려는 시도 나타냅니다 (예: 액세스 위반), 개체가 어떻게 하 든 올바르지 않으므로 (잘못 된 포인터 또는 코드 컴파일하지 와[/GR](../build/reference/gr-enable-run-time-type-information.md)).  
  
 경우는 *식* 은 포인터도 아니고 개체의 기본 클래스에 대 한 결과는 **type_info** 의 정적 형식을 나타내는 참조는 *식*. *정적 형식* 식의 형식을 참조 하는 식의 컴파일 타임에 알려진 합니다. 식의 정적 형식을 평가할 때 식의 의미 체계가 무시됩니다. 또한 식의 정적 형식을 결정할 때 가능할 경우 참조가 무시됩니다.  
  
```  
// expre_typeid_Operator_2.cpp  
#include <typeinfo>  
  
int main()  
{  
   typeid(int) == typeid(int&); // evaluates to true  
}  
```  
  
 **typeid** 사용할 수도 있습니다 템플릿에서 템플릿 매개 변수 형식을 확인할 수 있습니다.  
  
```  
// expre_typeid_Operator_3.cpp  
// compile with: /c  
#include <typeinfo>  
template < typename T >   
T max( T arg1, T arg2 ) {  
   cout << typeid( T ).name() << "s compared." << endl;  
   return ( arg1 > arg2 ? arg1 : arg2 );  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [런타임 형식 정보](../cpp/run-time-type-information.md)   
 [키워드](../cpp/keywords-cpp.md)
