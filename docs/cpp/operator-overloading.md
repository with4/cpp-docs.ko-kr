---
title: "연산자 오버 로드 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- operator_cpp
- operator
dev_langs:
- C++
helpviewer_keywords:
- redefinable operators [C++]
- non-redefinable operators [C++]
- operator keyword [C++]
- operators [C++], overloading
- operator overloading
ms.assetid: 56ad4c4f-dd0c-45e0-adaa-08fe98cb1f8e
caps.latest.revision: 13
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 5ac9415ec186760a70394772ffaff011d7c68c95
ms.contentlocale: ko-kr
ms.lasthandoff: 09/25/2017

---
# <a name="operator-overloading"></a>연산자 오버로드
`operator` 키워드는 `operator-symbol`이 클래스 인스턴스에 적용될 때의 의미를 지정하는 함수를 선언합니다. 이 키워드는 연산자에게 둘 이상의 의미를 제공 즉, 오버로드합니다. 컴파일러는 피연산자의 형식을 검사하여 연산자의 여러 가지 의미 간을 구분합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
type operator operator-symbol ( parameter-list )  
```  
  
## <a name="remarks"></a>설명  
 대부분의 기본 제공 연산자의 함수는 전역적으로 또는 클래스 단위로 다시 정의할 수 있습니다. 오버로드된 연산자는 함수로 구현됩니다.  
  
 오버 로드 된 연산자의 이름은 `operator x`여기서 `x` 다음 표에 표시 된 대로 연산자입니다. 예를 들어 더하기 연산자를 오버로드하려면 `operator+`라는 함수를 정의합니다. 마찬가지로, 더하기/할당 연산자 `+=`를 오버로드하려면 `operator+=`라는 함수를 정의합니다.  
  
### <a name="redefinable-operators"></a>다시 정의할 수 있는 연산자  
  
|연산자|이름|형식|  
|--------------|----------|----------|  
|`,`|쉼표|이항|  
|`!`|논리 NOT|단항|  
|`!=`|같지 않음|이항|  
|`%`|모듈러스|이항|  
|`%=`|모듈러스 대입|이항|  
|`&`|비트 AND|이항|  
|`&`|Address-of|단항|  
|`&&`|논리적 AND|이항|  
|`&=`|비트 AND 대입|이항|  
|`( )`|함수 호출 |—|  
|`( )`|캐스트 연산자|단항|  
|`*`|곱하기|이항|  
|`*`|포인터 역참조|단항|  
|`*=`|곱하기 할당|이항|  
|`+`|더하기|이항|  
|`+`|단항 더하기|단항|  
|`++`|증분 <sup>1</sup>|단항|  
|`+=`|더하기 할당|이항|  
|`-`|빼기|이항|  
|`-`|단항 부정 연산자|단항|  
|`--`|감소 <sup>1</sup>|단항|  
|`-=`|빼기 할당|이항|  
|`->`|멤버 선택|이항|  
|`->*`|멤버 포인터 선택|이항|  
|`/`|나누기|이항|  
|`/=`|나누기 할당|이항|  
|`<`|보다 작음|이항|  
|`<<`|왼쪽 <Shift>|이항|  
|`<<=`|왼쪽 시프트 할당|이항|  
|`<=`|작거나 같음|이항|  
|`=`|대입|이항|  
|`==`|같음|이항|  
|`>`|보다 큼|이항|  
|`>=`|크거나 같음|이항|  
|`>>`|오른쪽 Shift|이항|  
|`>>=`|오른쪽 시프트 할당|이항|  
|`[ ]`|배열 첨자|—|  
|`^`|배타적 OR|이항|  
|`^=`|배타적 OR 할당|이항|  
|`&#124;`|포괄적 비트 OR|이항|  
|`&#124;=`|포괄적 비트 OR 대입|이항|  
|`&#124;&#124;`|논리적 OR|이항|  
|`~`|1의 보수|단항|  
|`delete`|`Delete`|—|  
|`new`|`New`|—|  
|`conversion operators`|conversion operators|단항|  
  
 1 두 개 단항 증가 및 감소 연산자: 사전 증가 및 사후 증가 합니다.  
  
 참조 [연산자 오버 로드에 대 한 일반 규칙](../cpp/general-rules-for-operator-overloading.md) 자세한 정보에 대 한 합니다. 다양한 범주의 오버로드된 연산자에 대한 제약 조건이 다음 항목에 설명되어 있습니다.  
  
-   [단항 연산자](../cpp/overloading-unary-operators.md)  
  
-   [이항 연산자](../cpp/binary-operators.md)  
  
-   [할당](../cpp/assignment.md)  
  
-   [함수 호출](../cpp/function-call-cpp.md)  
  
-   [첨자](../cpp/subscripting.md)  
  
-   [클래스 멤버 액세스](../cpp/member-access.md)  
  
-   [증가 및 감소](../cpp/increment-and-decrement-operator-overloading-cpp.md)합니다.  
  
-   [사용자 정의 형식 변환](../cpp/user-defined-type-conversions-cpp.md)  
  
 다음 테이블의 연산자는 오버로드할 수 없습니다. 이 테이블에는 전처리기 기호인 `#` 및 `##` 기호가 포함됩니다.  
  
### <a name="nonredefinable-operators"></a>다시 정의할 수 없는 연산자  
  
|||  
|-|-|  
|`Operator`|`Name`|  
|`.`|멤버 선택|  
|`.*`|멤버 포인터 선택|  
|`::`|범위 확인|  
|`? :`|조건|  
|`#`|문자열로 전처리기 변환|  
|`##`|전처리기 연결|  
  
 오버로드된 연산자는 코드에서 발견되었을 때 일반적으로 컴파일러에 의해 암시적으로 호출되지만 다음과 같이 멤버 또는 비멤버 함수가 호출될 때처럼 명시적으로 호출할 수 있습니다.  
  
```  
Point pt;  
pt.operator+( 3 );  // Call addition operator to add 3 to pt.  
```  
  
## <a name="example"></a>예제  
 다음 예제에서는 `+` 연산자를 오버로드하여 두 개의 복소수를 추가하고 그 결과를 반환합니다.  
  
```  
// operator_overloading.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
struct Complex {  
   Complex( double r, double i ) : re(r), im(i) {}  
   Complex operator+( Complex &other );  
   void Display( ) {   cout << re << ", " << im << endl; }  
private:  
   double re, im;  
};  
  
// Operator overloaded using a member function  
Complex Complex::operator+( Complex &other ) {  
   return Complex( re + other.re, im + other.im );  
}  
  
int main() {  
   Complex a = Complex( 1.2, 3.4 );  
   Complex b = Complex( 5.6, 7.8 );  
   Complex c = Complex( 0.0, 0.0 );  
  
   c = a + b;  
   c.Display();  
}  
```  
  
## <a name="output"></a>출력  
  
```  
6.8, 11.2  
```  
  
## <a name="in-this-section"></a>단원 내용  
  
1.  [연산자 오버로드에 대한 일반 규칙](../cpp/general-rules-for-operator-overloading.md)  
  
2.  [단항 연산자 오버로드](../cpp/overloading-unary-operators.md)  
  
3.  [이항 연산자](../cpp/binary-operators.md)  
  
4.  [할당](../cpp/assignment.md)  
  
5.  [함수 호출](../cpp/function-call-cpp.md)  
  
6.  [첨자](../cpp/subscripting.md)  
  
7.  [멤버 액세스](../cpp/member-access.md)  
  
## <a name="see-also"></a>참고 항목  
 [C + + 기본 제공 연산자, 우선 순위 및 결합성](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [키워드](../cpp/keywords-cpp.md)
