---
title: "연산자 오버로드 | Microsoft Docs"
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
  - "operator_cpp"
  - "operator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "non-redefinable 연산자"
  - "operator 키워드[C++]"
  - "연산자 오버로드"
  - "연산자[C++], 오버로드"
  - "재정의 가능 연산자"
ms.assetid: 56ad4c4f-dd0c-45e0-adaa-08fe98cb1f8e
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 연산자 오버로드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`operator` 키워드는 `operator-symbol`이 클래스 인스턴스에 적용될 때의 의미를 지정하는 함수를 선언합니다.  이 키워드는 연산자에게 둘 이상의 의미를 제공 즉, 오버로드합니다.  컴파일러는 피연산자의 형식을 검사하여 연산자의 여러 가지 의미 간을 구분합니다.  
  
## 구문  
  
```  
  
type operator operator-symbol ( parameter-list )  
```  
  
## 설명  
 대부분의 기본 제공 연산자의 함수는 전역적으로 또는 클래스 단위로 다시 정의할 수 있습니다.  오버로드된 연산자는 함수로 구현됩니다.  
  
 오버로드된 연산자의 이름은 `operator``x`이며 여기서 `x`는 다음 테이블에 나와 있는 연산자입니다.  예를 들어 더하기 연산자를 오버로드하려면 `operator+`라는 함수를 정의합니다.  마찬가지로, 더하기\/할당 연산자 `+=`를 오버로드하려면 `operator+=`라는 함수를 정의합니다.  
  
### 다시 정의할 수 있는 연산자  
  
|연산자|이름|형식|  
|---------|--------|--------|  
|`,`|쉼표|이항|  
|`!`|논리 NOT|단항|  
|`!=`|같지 않음|이항|  
|`%`|모듈러스|이항|  
|`%=`|모듈러스 대입|이항|  
|`&`|비트 AND|이항|  
|`&`|Address\-of|단항|  
|`&&`|논리적 AND|이항|  
|`&=`|비트 AND 대입|이항|  
|`( )`|함수 호출|—|  
|`( )`|캐스트 연산자|단항|  
|`*`|곱하기|이항|  
|`*`|포인터 역참조|단항|  
|`*=`|곱하기 할당|이항|  
|`+`|더하기|이항|  
|`+`|단항 더하기|단항|  
|`++`|증가 <sup>1</sup>|단항|  
|`+=`|더하기 할당|이항|  
|`–`|빼기|이항|  
|`–`|단항 부정 연산자|단항|  
|`––`|감소 <sup>1</sup>|단항|  
|`–=`|빼기 할당|이항|  
|`–>`|멤버 선택|이항|  
|`–>*`|멤버 포인터 선택|이항|  
|`/`|나눗셈 기호|이항|  
|`/=`|나누기 할당|이항|  
|`<`|보다 작음|이항|  
|`<<`|왼쪽 \<Shift\>|이항|  
|`<<=`|왼쪽 시프트 할당|이항|  
|`<=`|작거나 같음|이항|  
|`=`|할당|이항|  
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
  
 1   단항 증가 및 감소 연산자에는 두 가지 버전 즉, 사전 증가 및 사후 증가가 있습니다.  
  
 자세한 내용은 [연산자 오버로드에 대한 일반 규칙](../cpp/general-rules-for-operator-overloading.md)을 참조하세요.  다양한 범주의 오버로드된 연산자에 대한 제약 조건이 다음 항목에 설명되어 있습니다.  
  
-   [단항 연산자](../cpp/overloading-unary-operators.md)  
  
-   [이항 연산자](../cpp/binary-operators.md)  
  
-   [할당](../cpp/assignment.md)  
  
-   [함수 호출](../cpp/function-call-cpp.md)  
  
-   [첨자](../cpp/subscripting.md)  
  
-   [클래스 멤버 액세스](../cpp/member-access.md)  
  
-   [증가 및 감소](../cpp/increment-and-decrement-operator-overloading-cpp.md)  
  
-   [변환](../cpp/user-defined-type-conversions-cpp.md)  
  
 다음 테이블의 연산자는 오버로드할 수 없습니다.  이 테이블에는 전처리기 기호인 `#` 및 `##` 기호가 포함됩니다.  
  
### 다시 정의할 수 없는 연산자  
  
|||  
|-|-|  
|`Operator`|`Name`|  
|`.`|멤버 선택|  
|`.*`|멤버 포인터 선택|  
|`::`|범위 확인|  
|`?  :`|조건|  
|`#`|문자열로 전처리기 변환|  
|`##`|전처리기 연결|  
  
 오버로드된 연산자는 코드에서 발견되었을 때 일반적으로 컴파일러에 의해 암시적으로 호출되지만 다음과 같이 멤버 또는 비멤버 함수가 호출될 때처럼 명시적으로 호출할 수 있습니다.  
  
```  
Point pt;  
pt.operator+( 3 );  // Call addition operator to add 3 to pt.  
```  
  
## 예제  
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
  
## 출력  
  
```  
6.8, 11.2  
```  
  
## 단원 내용  
  
1.  [연산자 오버로드에 대한 일반 규칙](../cpp/general-rules-for-operator-overloading.md)  
  
2.  [단항 연산자 오버로드](../cpp/overloading-unary-operators.md)  
  
3.  [이항 연산자](../cpp/binary-operators.md)  
  
4.  [할당](../cpp/assignment.md)  
  
5.  [함수 호출](../cpp/function-call-cpp.md)  
  
6.  [첨자](../cpp/subscripting.md)  
  
7.  [멤버 액세스](../cpp/member-access.md)  
  
## 참고 항목  
 [C\+\+ 연산자](../misc/cpp-operators.md)   
 [C\+\+ 키워드](../cpp/keywords-cpp.md)