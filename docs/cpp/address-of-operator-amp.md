---
title: "주소 연산자: &amp; | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- '&'
dev_langs:
- C++
helpviewer_keywords:
- address-of operator (&)
- '& operator'
- '& operator, address-of operator'
ms.assetid: 2828221a-15f6-4acc-87fe-25e34feebb88
caps.latest.revision: 7
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
ms.openlocfilehash: 56e2606759cc381c1ae6f6f4f1f7cbc1d9d2d810
ms.contentlocale: ko-kr
ms.lasthandoff: 09/25/2017

---
# <a name="address-of-operator-amp"></a>주소 연산자:&amp;
## <a name="syntax"></a>구문  
  
```  
& cast-expression  
```  
  
## <a name="remarks"></a>설명  
 단항 address-of 연산자 (**&**)는 피연산자의 주소를 사용 합니다. 주소 연산자의 피연산자는 함수 지정자 또는 l-value가 될 수 있습니다. 이때, l-value가 지정하는 개체는 비트 필드가 아니며 **register** 저장소 클래스 지정자로 선언되지 않습니다.  
  
 주소 연산자는 파일 범위 수준에서 선언된 기본, 구조체, 클래스 또는 공용 구조체 형식의 변수 또는 첨자된 배열 참조에만 적용될 수 있습니다. 이러한 식에서는 주소 연산자가 없는 상수 식을 주소 식에 추가하거나 뺄 수 있습니다.  
  
 함수 또는 l-value에 적용된 식의 결과는 피연산자의 형식에서 파생된 포인터 형식(r-value)입니다. 예를 들어, 피연산자의 형식이 `char`인 경우 식의 결과 형식은 `char`의 포인터 형식입니다. 에 적용 된 address-of 연산자 **const** 또는 `volatile` 개체, 조건이 **const** `type` ** \* ** 또는 `volatile` `type` ** \* **여기서 `type` 원래 개체의 형식입니다.  
  
 Address-of 연산자에 적용 된 경우는 [정규화 된 이름](http://msdn.microsoft.com/en-us/3fefb16d-8120-4627-8b3f-3d90fbdcd1df), 여부에 따라 결과가 결정는 *정규화 된 이름이* 정적 멤버를 지정 합니다. 그럴 경우 결과는 멤버의 선언에 지정된 형식의 포인터입니다. 결과 멤버가 정적 인지, 멤버에 대 한 포인터는 *이름* 으로 표시 되는 클래스의 *정규화 된 클래스 이름*합니다. (참조 [기본 식](../cpp/primary-expressions.md) 에 대 한 자세한 *정규화 된 클래스 이름*.) 다음 코드는 멤버가 정적인지 여부에 따라 결과가 달라지는 방식을 보여 줍니다.  
  
```  
// expre_Address_Of_Operator.cpp  
// C2440 expected  
class PTM {  
public:  
           int   iValue;  
    static float fValue;  
};  
  
int main() {  
   int   PTM::*piValue = &PTM::iValue;  // OK: non-static  
   float PTM::*pfValue = &PTM::fValue;  // C2440 error: static  
   float *spfValue     = &PTM::fValue;  // OK  
}  
```  
  
 이 예제에서 `&PTM::fValue` 식은 `float *`가 정적 멤버이기 때문에 `float PTM::*` 형식이 아닌 `fValue` 형식이 됩니다.  
  
 오버로드된 함수의 주소는 어느 버전의 함수를 참조하는지 분명할 때에만 사용할 수 있습니다. 참조 [함수 오버 로드](function-overloading.md) 특정의 주소를 확인 하는 방법에 대 한 정보에 대 한 오버 로드 된 함수입니다.  
  
 주소 연산자를 참조 형식에 적용하면 해당 연산자를 참조가 바인딩된 개체에 적용하는 것과 같은 결과가 도출됩니다. 예:  
  
## <a name="example"></a>예제  
  
```  
// expre_Address_Of_Operator2.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
int main() {  
   double d;        // Define an object of type double.  
   double& rd = d;  // Define a reference to the object.  
  
   // Obtain and compare their addresses  
   if( &d == &rd )  
      cout << "&d equals &rd" << endl;  
}  
```  
  
## <a name="output"></a>출력  
  
```  
&d equals &rd  
```  
  
 다음 예제에서는 주소 연산자를 사용하여 포인터 인수를 함수에 전달합니다.  
  
```  
// expre_Address_Of_Operator3.cpp  
// compile with: /EHsc  
// Demonstrate address-of operator &  
  
#include <iostream>  
using namespace std;  
  
// Function argument is pointer to type int  
int square( int *n ) {  
   return (*n) * (*n);  
}  
  
int main() {  
   int mynum = 5;  
   cout << square( &mynum ) << endl;   // pass address of int  
}  
```  
  
## <a name="output"></a>출력  
  
```  
25  
```  
  
## <a name="see-also"></a>참고 항목  
 [단항 연산자가 있는 식](../cpp/expressions-with-unary-operators.md)   
 [C + + 기본 제공 연산자, 우선 순위 및 결합성](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Lvalue 참조 선언 자: &](../cpp/lvalue-reference-declarator-amp.md)   
 [연산자 주소 및 간접 참조](../c-language/indirection-and-address-of-operators.md)

