---
title: "주소 연산자: &amp; | Microsoft Docs"
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
  - "address-of"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "& 연산자"
  - "& 연산자, 주소 연산자"
  - "주소 연산자(&)"
ms.assetid: 2828221a-15f6-4acc-87fe-25e34feebb88
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 주소 연산자: &amp;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 구문  
  
```  
  
& cast-expression  
```  
  
## 설명  
 단항 주소 연산자\(**&**\)는 해당 피연산자의 주소를 사용합니다.  주소 연산자의 피연산자는 함수 지정자 또는 l\-value가 될 수 있습니다. 이때, l\-value가 지정하는 개체는 비트 필드가 아니며 **등록** 저장소 클래스 지정자로 선언되지 않습니다.  
  
 주소 연산자는 파일 범위 수준에서 선언된 기본, 구조체, 클래스 또는 공용 구조체 형식의 변수 또는 첨자된 배열 참조에만 적용될 수 있습니다.  이러한 식에서는 주소 연산자가 없는 상수 식을 주소 식에 추가하거나 뺄 수 있습니다.  
  
 함수 또는 l\-value에 적용된 식의 결과는 피연산자의 형식에서 파생된 포인터 형식\(r\-value\)입니다.  예를 들어, 피연산자의 형식이 `char`인 경우 식의 결과 형식은 `char`의 포인터 형식입니다.  **const** 또는 `volatile` 개체에 적용된 주소 연산자는 **const** `type` **\*** 또는 `volatile` `type` **\***로 계산됩니다. 이때 `type`는 원래 개체 유형입니다.  
  
 주소 연산자가 [정규화된 이름](http://msdn.microsoft.com/ko-kr/3fefb16d-8120-4627-8b3f-3d90fbdcd1df)에 적용되면, 결과는 정규화된 이름이 정적 멤버를 지정하는지 여부에 따라 달라집니다.  그럴 경우 결과는 멤버의 선언에 지정된 형식의 포인터입니다.  정적 멤버가 아닌 경우 결과는 *정규화된 클래스 이름*에서 표시한 클래스의 멤버 이름의 포인터입니다. *정규화된 클래스 이름*에 대한 자세한 내용은 [기본 식](../cpp/primary-expressions.md)을 참조하십시오. 다음 코드는 멤버가 정적인지 여부에 따라 결과가 달라지는 방식을 보여 줍니다.  
  
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
  
 이 예제에서 `&PTM::fValue` 식은 `fValue`가 정적 멤버이기 때문에 `float PTM::*` 형식이 아닌 `float *` 형식이 됩니다.  
  
 오버로드된 함수의 주소는 어느 버전의 함수를 참조하는지 분명할 때에만 사용할 수 있습니다.  오버로드된 특정 함수의 주소를 가져오는 방법에 대한 자세한 내용은 [오버로드된 함수 주소](../misc/address-of-overloaded-functions.md)를 참조하십시오.  
  
 주소 연산자를 참조 형식에 적용하면 해당 연산자를 참조가 바인딩된 개체에 적용하는 것과 같은 결과가 도출됩니다.  예를 들면 다음과 같습니다.  
  
## 예제  
  
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
  
## Output  
  
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
  
## Output  
  
```  
25  
```  
  
## 참고 항목  
 [단항 연산자가 있는 식](../cpp/expressions-with-unary-operators.md)   
 [C\+\+ 연산자](../misc/cpp-operators.md)   
 [C\+\+ 연산자, 우선 순위 및 결합성](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Lvalue 참조 선언자: &](../cpp/lvalue-reference-declarator-amp.md)   
 [연산자 주소 및 간접 참조](../c-language/indirection-and-address-of-operators.md)