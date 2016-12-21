---
title: "const (C++) | Microsoft Docs"
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
  - "const_cpp"
  - "const"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "const 키워드[C++]"
ms.assetid: b21c0271-1ad0-40a0-b21c-5e812bba0318
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# const (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

데이터 선언을 수정할 때 **const** 키워드는 개체 또는 변수를 수정할 수 없도록 지정합니다.  
  
## 구문  
  
```  
  
        const declaration ;  
member-function const ;  
```  
  
## const 값  
 **const** 키워드는 변수의 값이 상수임을 지정하고 프로그래머가 이 변수를 수정하지 못하게 하도록 컴파일러에 지시합니다.  
  
```  
// constant_values1.cpp  
int main() {  
   const int i = 5;  
   i = 10;   // C3892  
   i++;   // C2105  
}  
```  
  
 C\+\+에서 **\#define** 전처리기 지시문 대신 [const](../preprocessor/hash-define-directive-c-cpp.md) 키워드를 사용하여 상수 값을 정의할 수 있습니다.  **const**를 사용하여 정의된 값에는 형식 검사가 적용되며, 이 값을 상수 식 대신 사용할 수 있습니다.  C\+\+에서 다음과 같이 **const** 변수로 배열의 크기를 지정할 수 있습니다.  
  
```  
// constant_values2.cpp  
// compile with: /c  
const int maxarray = 255;  
char store_char[maxarray];  // allowed in C++; not allowed in C  
```  
  
 C에서 상수 값은 기본적으로 외부 링크로 설정되므로 소스 파일에만 나타날 수 있습니다.  C\+\+에서 상수 값은 기본적으로 내부 링크로 설정되므로 헤더 파일에 나타날 수 있습니다.  
  
 **const** 키워드는 포인터 선언에서도 사용할 수 있습니다.  
  
```  
// constant_values3.cpp  
int main() {  
   char *mybuf = 0, *yourbuf;  
   char *const aptr = mybuf;  
   *aptr = 'a';   // OK  
   aptr = yourbuf;   // C3892  
}  
```  
  
 **const**로 선언된 변수에 대한 포인터는 **const**로 선언된 포인터에만 할당될 수 있습니다.  
  
```  
// constant_values4.cpp  
#include <stdio.h>  
int main() {  
   const char *mybuf = "test";  
   char *yourbuf = "test2";  
   printf_s("%s\n", mybuf);  
  
   const char *bptr = mybuf;   // Pointer to constant data  
   printf_s("%s\n", bptr);  
  
   // *bptr = 'a';   // Error  
}  
```  
  
 상수 데이터에 대한 포인터를 함수 매개 변수로 사용하여 함수가 포인터를 통해 전달된 매개 변수를 수정하지 못하게 할 수 있습니다.  
  
 **const**로 선언된 개체의 경우 [상수 멤버 함수](../misc/constant-member-functions.md)만 호출할 수 있습니다.  이렇게 하면 상수 개체가 절대로 수정되지 않습니다.  
  
```  
birthday.getMonth();    // Okay  
birthday.setMonth( 4 ); // Error  
```  
  
 비상수 개체의 경우에는 상수 또는 비상수 멤버 함수를 호출할 수 있습니다.  **const** 키워드를 사용하여 멤버 함수를 오버로드할 수도 있으며, 이에 따라 상수 및 비상수 개체에 대해 다른 버전의 함수를 호출할 수 있습니다.  
  
 **const** 키워드를 사용하여 생성자나 소멸자를 선언할 수 없습니다.  
  
## const 멤버 함수  
 **const** 키워드로 멤버 함수를 선언하면 함수가 자신이 호출되는 개체를 수정하지 않는 "읽기 전용" 함수로 지정됩니다.  상수 멤버 함수는 비정적 데이터 멤버를 수정하거나 상수가 아닌 멤버 함수를 호출할 수 없습니다. 상수 멤버 함수를 선언하려면 인수 목록의 닫는 괄호 뒤에 **const** 키워드를 배치합니다.  **const** 키워드는 선언과 정의 모두에서 필요합니다.  
  
```  
// constant_member_function.cpp  
class Date  
{  
public:  
   Date( int mn, int dy, int yr );  
   int getMonth() const;     // A read-only function  
   void setMonth( int mn );   // A write function; can't be const  
private:  
   int month;  
};  
  
int Date::getMonth() const  
{  
   return month;        // Doesn't modify anything  
}  
void Date::setMonth( int mn )  
{  
   month = mn;          // Modifies data member  
}  
int main()  
{  
   Date MyDate( 7, 4, 1998 );  
   const Date BirthDate( 1, 18, 1953 );  
   MyDate.setMonth( 4 );    // Okay  
   BirthDate.getMonth();    // Okay  
   BirthDate.setMonth( 4 ); // C2662 Error  
}  
```  
  
## C 및 C\+\+ const 차이점  
 C 소스 코드 파일에서 변수를 **const**로 선언할 때 다음과 같이 선언합니다.  
  
```  
const int i = 2;  
```  
  
 그런 다음 이 변수를 아래와 같이 다른 모듈에서 사용할 수 있습니다.  
  
```  
extern const int i;  
```  
  
 그러나 C\+\+에서 동일한 동작을 얻으려면 **const** 변수를 다음과 같이 선언해야 합니다.  
  
```  
extern const int i = 2;  
```  
  
 C 소스 코드 파일에 사용하기 위해 C\+\+ 소스 코드 파일에서 `extern` 변수를 선언하려면 다음 코드를 사용하여  
  
```  
extern "C" const int x=10;  
```  
  
 C\+\+ 컴파일러에 의한 이름 변환을 방지해야 합니다.  
  
## 설명  
 멤버 함수의 매개 변수 목록을 따를 때 **const** 키워드는 함수가 자신이 호출되는 개체를 수정하지 않도록 지정합니다.  
  
 **const**에 대한 자세한 내용은 다음 항목을 참조하세요.  
  
-   [상수 값](../misc/constant-values.md)  
  
-   [상수 멤버 함수](../misc/constant-member-functions.md)  
  
-   [const 및 volatile 포인터](../cpp/const-and-volatile-pointers.md)  
  
-   [형식 한정자\(C 언어 참조\)](../c-language/type-qualifiers.md)  
  
-   [volatile](../cpp/volatile-cpp.md)  
  
-   [\#define](../preprocessor/hash-define-directive-c-cpp.md).  
  
## 참고 항목  
 [C\+\+ 키워드](../cpp/keywords-cpp.md)