---
title: const (c + +) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- const_cpp
- const
dev_langs:
- C++
helpviewer_keywords:
- const keyword [C++]
ms.assetid: b21c0271-1ad0-40a0-b21c-5e812bba0318
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
ms.openlocfilehash: 8a6a238f28ec8f84cd127b4af88a84edb26506ee
ms.contentlocale: ko-kr
ms.lasthandoff: 09/25/2017

---
# <a name="const-c"></a>const (C++)
데이터 선언을 수정할 때는 **const** 키워드는 개체 또는 변수를 수정할 수를 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      const declaration ;  
member-function const ;  
```  
  
## <a name="const-values"></a>const 값  
 **const** 변수 값 상수 이며 프로그래머는 수정 되지 않도록 하려면 컴파일러가 키워드를 지정 합니다.  
  
```  
// constant_values1.cpp  
int main() {  
   const int i = 5;  
   i = 10;   // C3892  
   i++;   // C2105  
}  
```  
  
 C + +에서는 사용할 수 있습니다는 **const** 대신 키워드는 [#define](../preprocessor/hash-define-directive-c-cpp.md) 전처리기 지시문을 상수 값을 정의 합니다. 값으로 정의 된 **const** 형식 검사가 적용 되며 상수 식 대신 사용할 수 있습니다. C + +에서는와 배열 크기를 지정할 수 있습니다는 **const** 다음과 같이 변수:  
  
```  
// constant_values2.cpp  
// compile with: /c  
const int maxarray = 255;  
char store_char[maxarray];  // allowed in C++; not allowed in C  
```  
  
 C에서 상수 값은 기본적으로 외부 링크로 설정되므로 소스 파일에만 나타날 수 있습니다. C++에서 상수 값은 기본적으로 내부 링크로 설정되므로 헤더 파일에 나타날 수 있습니다.  
  
 **const** 포인터 선언에서 키워드를 사용할 수도 있습니다.  
  
```  
// constant_values3.cpp  
int main() {  
   char *mybuf = 0, *yourbuf;  
   char *const aptr = mybuf;  
   *aptr = 'a';   // OK  
   aptr = yourbuf;   // C3892  
}  
```  
  
 으로 선언 된 변수에 대 한 포인터 **const** 로 선언 된 포인터에만 할당할 수 **const**합니다.  
  
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
  
 로 선언 된 개체에 대 한 **const**, 있습니다 수만 상수 멤버 함수를 호출 합니다. 이렇게 하면 상수 개체가 절대로 수정되지 않습니다.  
  
```  
birthday.getMonth();    // Okay  
birthday.setMonth( 4 ); // Error  
```  
  
 비상수 개체의 경우에는 상수 또는 비상수 멤버 함수를 호출할 수 있습니다. 사용 하 여 멤버 함수는 오버 로드할 수도 있으며는 **const** 키워드입니다; 이렇게 하면 다른 버전의 상수 및 비상수 개체에 대해 호출할 함수입니다.  
  
 여 생성자 나 소멸자를 선언할 수 없습니다는 **const** 키워드입니다.  
  
## <a name="const-member-functions"></a>const 멤버 함수  
 멤버 함수를 선언 하는 **const** 키워드는 함수는 호출 하는 개체를 수정 하지 않는 "읽기 전용" 함수로 지정 합니다. 상수 멤버 함수는 비정적 데이터 멤버를 수정 하거나 멤버 상수 없는 함수를 호출할 수 없습니다. 상수 멤버 함수를 선언 하려면 배치는 **const** 인수 목록의 닫는 괄호 뒤 키워드입니다. **const** 키워드는 선언과 정의 둘 다 필요 합니다.  
  
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
  
## <a name="c-and-c-const-differences"></a>C 및 C++ const 차이점  
 변수를 선언할 때 **const** C 소스 코드 파일에서 이렇게 하면로:  
  
```  
const int i = 2;  
```  
  
 그런 다음 이 변수를 아래와 같이 다른 모듈에서 사용할 수 있습니다.  
  
```  
extern const int i;  
```  
  
 C + +에서 동일한 동작을 가져오려면 선언 해야 하지만 프로그램 **const** 으로 변수:  
  
```  
extern const int i = 2;  
```  
  
 C 소스 코드 파일에 사용하기 위해 C++ 소스 코드 파일에서 `extern` 변수를 선언하려면 다음 코드를 사용하여  
  
```  
extern "C" const int x=10;  
```  
  
 C++ 컴파일러에 의한 이름 변환을 방지해야 합니다.  
  
## <a name="remarks"></a>설명  
 매개 변수 목록 멤버 함수를 수행할 때의 **const** 키워드 지정 함수를 호출 하는 개체를 수정 하지 않습니다.  
  
 대 한 자세한 내용은 **const**, 다음 항목을 참조 합니다.  
    
-   [const 및 volatile 포인터](../cpp/const-and-volatile-pointers.md)  
  
-   [형식 한정자 (C 언어 참조)](../c-language/type-qualifiers.md)  
  
-   [volatile](../cpp/volatile-cpp.md)  
  
-   [#define](../preprocessor/hash-define-directive-c-cpp.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [키워드](../cpp/keywords-cpp.md)
