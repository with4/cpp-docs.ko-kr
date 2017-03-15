---
title: "C 및 C++에 대한 Microsoft 확장 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "! operator, C++ 확장"
  - "!= 연산자"
  - "& 연산자, C/C++ 확장"
  - "&amp;&amp; 연산자"
  - "&= 연산자"
  - "^ 연산자, C/C++ 확장"
  - "^= 연산자, C++ 확장"
  - "| 연산자, 확장"
  - "|| 연산자"
  - "|= 연산자"
  - "~ 연산자, C/C++ 확장"
  - "And 연산자, C/C++ 확장"
  - "and_eq 연산자"
  - "compl 메서드"
  - "확장"
  - "확장, C 언어"
  - "iso646.h 헤더"
  - "C/C++에 대한 Microsoft 확장"
  - "NOT 연산자"
  - "not_eq 연산자"
  - "Or 연산자, C/C++에 대한 Microsoft 확장"
  - "or_eq 연산자"
  - "Visual C, Microsoft 확장"
  - "Visual C++, C/C++ 확장"
  - "Xor 연산자, C/C++에 대한 Microsoft 확장"
  - "xor_eq 연산자"
ms.assetid: e811a74a-45ba-4c00-b206-2f2321b8689a
caps.latest.revision: 18
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# C 및 C++에 대한 Microsoft 확장
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+ 다음과 같이 ANSI C 및 c \+ \+ ANSI 표준을 확장합니다.  
  
## 키워드  
 여러 키워드가 추가됩니다.  다음 [C\+\+ 키워드](../../cpp/keywords-cpp.md)의 목록에서, 두 선행 밑줄이 있는 키워드는 Visual C\+\+ 확장입니다.  
  
## static const 정수 계열\(또는 열거형\) 멤버의 Out\-of\-Class 정의  
 표준\(**\/Za**\) 옵션에서는 여기서 보여지는 것과 같이 데이터 멤버에 대해 out\-of\-class를 정의해야 합니다.  
  
```  
class CMyClass  {  
   static const int max = 5;  
   int m_array[max];  
}  
...  
const int CMyClass::max;   // out of class definition  
```  
  
 **\/Ze**를 사용하면 static const 정수 계열 및 const 열거형 데이터 멤버에 대해 선택적으로 out\-of\-class를 정의할 수도 있고 정의하지 않을 수도 있습니다.  static 및 const인 정수 계열과 열거형만이 클래스 내부에서 초기 값을 가질 수 있으며, 초기화 식은 const 식이어야 합니다.  
  
 헤더 파일에서 아웃 클래스 정의가 제공되고 여러 소스 파일에 헤더 파일이 포함된 경우 오류가 발생하지 않으려면, [selectany](../../cpp/selectany.md)을 사용합니다.  예를 들면 다음과 같습니다.  
  
```  
__declspec(selectany) const int CMyClass::max = 5;  
```  
  
## 캐스트  
 C 컴파일러와 C \+ \+ 컴파일러는 이러한 유형의 비 ANSI 캐스트를 지원합니다.  
  
-   l\-values를 산출하기 위한 비ANSI 캐스트입니다.  예를 들면 다음과 같습니다.  
  
    ```  
    char *p;  
    (( int * ) p )++;  
    ```  
  
    > [!NOTE]
    >  이 확장은 C 언어만 사용할 수 있습니다.  다른 형식을 지정하는 포인터를 수정하기 위한 C \+ \+ 코드에서 ANSI C 표준 형식을 사용할 수 있습니다.  
  
     앞의 예제를 다음과 같이 ANSI C 표준에 맞게 다시 작성할 수 있습니다.  
  
    ```  
    p = ( char * )(( int * )p + 1 );  
    ```  
  
-   함수 포인터를 데이터 포인터로 캐스팅하는 비ANSI  예를 들면 다음과 같습니다.  
  
    ```  
    int ( * pfunc ) ();   
    int *pdata;  
    pdata = ( int * ) pfunc;  
    ```  
  
     ANSI 규격을 유지하면서 동일한 캐스트를 수행하려면, 함수 포인터를 데이터 포인터로 캐스팅하기 전에 `uintptr_t` 로 캐스팅해야 합니다.  
  
    ```  
    pdata = ( int * ) (uintptr_t) pfunc;  
    ```  
  
## 가변 길이 인수 목록  
 C \+ \+컴파일러와 C 컴파일러는 다양한 수의 인수가 지정되는 함수 선언자 사용을 지원하며, 대신 이 뒤에는 형식을 제공하는 함수 정의가 옵니다.  
  
```  
void myfunc( int x, ... );  
void myfunc( int x, char * c )  
{ }  
```  
  
## 한 줄로 된 주석  
 C 컴파일러는 앞에 두 개의 슬래시\(\/\/\) 문자가 있는 한 줄로 된 주석을 지원합니다.  
  
```  
// This is a single-line comment.  
```  
  
## 범위  
 C 컴파일러는 다음과 같은 범위 관련 기능을 지원합니다.  
  
-   extern 항목을 static으로 재정의  
  
    ```  
    extern int clip();  
    static int clip()  
    {}  
    ```  
  
-   같은 범위 내에서 typedef 재정의 사용  
  
    ```  
    typedef int INT;  
    typedef int INT;  
    ```  
  
-   파일 범위의 함수 선언자  
  
    ```  
    void func1()  
    {  
        extern int func2( double );  
    }  
    int main( void )  
    {  
        func2( 4 );    //  /Ze passes 4 as type double  
    }                  //  /Za passes 4 as type int  
    ```  
  
-   비상수 식을 사용하여 초기화 된 블록 범위의 변수를 사용:  
  
    ```  
    int clip( int );  
    int bar( int );  
    int main( void )  
    {  
        int array[2] = { clip( 2 ), bar( 4 ) };  
    }  
    int clip( int x )  
    {  
        return x;  
    }  
    int bar( int x )  
    {  
        return x;  
    }  
    ```  
  
## 데이터 선언 및 정의  
 C 컴파일러는 다음과 같은 데이터 선언 및 정의 기능을 지원합니다.  
  
-   이니셜라이저에서 문자 및 문자열 상수 혼합 사용  
  
    ```  
    char arr[5] = {'a', 'b', "cde"};  
    ```  
  
-   비트 필드는 기본 형식 이외의 **unsigned int** 또는 **signed int**를 갖습니다.  
  
-   형식을 사용하지 않는 선언자.  
  
    ```  
    x;  
    int main( void )  
    {  
        x = 1;  
    }  
    ```  
  
-   구조체와 공용 구조체의 마지막 필드로 크기를 지정하지 않은 배열 사용  
  
    ```  
    struct zero  
    {  
        char *c;  
        int zarray[];  
    };  
    ```  
  
-   명명되지 않은\(익명\) 구조체  
  
    ```  
    struct  
    {  
        int i;  
        char *s;  
    };  
    ```  
  
-   명명되지 않은\(익명\) 공용 구조체  
  
    ```  
    union  
    {  
        int i;  
        float fl;  
    };  
    ```  
  
-   명명되지 않은 멤버  
  
    ```  
    struct s  
    {  
       unsigned int flag : 1;  
       unsigned int : 31;  
    }  
    ```  
  
## 내장 부동 소수점 함수  
 **\/Oi** 이 지정된 경우, C \+ \+ 컴파일러와 C 컴파일러는 `atan`, `atan2`, `cos`, `exp`, `log`, `log10`, `sin`, `sqrt`, 및 `tan` 함수 **END x86 Specific** 의 인라인 생성 **x87 Specific \>** 을 지원합니다.  C 컴파일러의 경우, ANSI 규칙은 `errno` 변수를 설정하지 않기 때문에 이러한 내장 함수가 사용될 때 적용되지 않습니다.  
  
## 비 Const 포인터 매개 변수를 Const 포인터 매개 변수 참조를 원하는 함수에 전달  
 이는 C\+\+에 대한 확장입니다.  이 코드는 **\/Ze**를 사용하여 컴파일합니다:  
  
```  
typedef   int   T;  
  
const T  acT = 9;      // A constant of type 'T'  
const T* pcT = &acT;   // A pointer to a constant of type 'T'  
  
void func2 ( const T*& rpcT )   // A reference to a pointer to a constant of type 'T'  
{  
   rpcT = pcT;  
}  
  
T*   pT;               // A pointer to a 'T'  
  
void func ()  
{  
   func2 ( pT );      // Should be an error, but isn't detected  
   *pT   = 7;         // Invalidly overwrites the constant 'acT'  
}  
```  
  
## ISO646.H를 사용할 수 없음  
 **\/Ze** 옵션을 사용할 경우 텍스트 서식의 다음 연산자를 사용하려면 iso646.h를 포함해야 합니다.  
  
-   && \(and\)  
  
-   &\= \(and\_eq\)  
  
-   & \(bitand\)  
  
-   &#124; \(bitor\)  
  
-   ~ \(compl\)  
  
-   \! \(not\)  
  
-   \!\= \(not\_eq\)  
  
-   &#124;&#124; \(or\)  
  
-   &#124;\= \(or\_eq\)  
  
-   ^ \(xor\)  
  
-   ^\= \(xor\_eq\)  
  
## 문자열 리터럴 주소 형식은 const char \(\*\) \[\]가 아닌 const char \[\]이다.  
 다음 예제 코드는 **\/Za**가 지정된 경우에는 char const \(\*\)\[4\]를 출력하지만 **\/Ze**가 지정된 경우에는 char const \[4\]를 출력합니다.  
  
```  
#include <stdio.h>  
#include <typeinfo>  
  
int main()  
{  
    printf_s("%s\n", typeid(&"abc").name());  
}  
```  
  
## 참고 항목  
 [\/Za, \/Ze\(언어 확장 사용 안 함\)](../../build/reference/za-ze-disable-language-extensions.md)   
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)