---
title: "컴파일러 오류 C2666 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2666"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2666"
ms.assetid: 78364d15-c6eb-439a-9088-e04a0176692b
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2666
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : number개 오버로드에 비슷한 변환이 있습니다.  
  
 오버로드된 함수 또는 연산자가 모호합니다.   여러 정식 매개 변수 목록이 비슷하여 컴파일러가 모호성을 해결할 수 없습니다.  이 오류를 해결하려면 하나 이상의 실제 매개 변수를 명시적으로 캐스팅하십시오.  
  
 다음 샘플에서는 C2666 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2666.cpp  
struct complex {  
   complex(double);  
};  
  
void h(int,complex);  
void h(double, double);  
  
int main() {  
   h(3,4);   // C2666  
}  
```  
  
 이 오류는 또한 Visual Studio .NET 2003에서 컴파일러 규칙에 따른 작업을 수행한 결과로 발생할 수 있습니다.  
  
-   이항 연산자와 포인터 형식으로의 사용자 정의 변환  
  
-   한정 변환과 동일 변환의 차이  
  
 이항 연산자 \<, \>, \<\=, and \>\=의 경우, 이제 해당 피연산자의 형식으로 변환하도록 사용자 정의 변환 연산자가 매개 변수의 형식에 정의되어 있으면 전달되는 매개 변수는 해당 피연산자의 형식으로 암시적으로 변환됩니다.  따라서 잠재적으로 모호성이 발생할 수 있습니다.  
  
 Visual Studio .NET 2003과 Visual Studio .NET 버전의 Visual C\+\+ 모두에서 올바른 코드가 되도록 하려면 함수 구문을 명시적으로 사용하여 클래스 연산자를 호출하십시오.  
  
## 예제  
  
```  
// C2666b.cpp  
#include <string.h>  
#include <stdio.h>  
  
struct T   
{  
    T( const T& copy )   
    {  
        m_str = copy.m_str;  
    }  
  
    T( const char* str )   
    {  
        int iSize = (strlen( str )+ 1);  
        m_str = new char[ iSize ];  
        if (m_str)  
            strcpy_s( m_str, iSize, str );  
    }  
  
    bool operator<( const T& RHS )   
    {  
        return m_str < RHS.m_str;  
    }  
  
    operator char*() const   
    {  
        return m_str;  
    }  
  
    char* m_str;  
};  
  
int main()   
{  
    T str1( "ABCD" );  
    const char* str2 = "DEFG";  
  
    // Error – Ambiguous call to operator<()  
    // Trying to convert str1 to char* and then call   
    // operator<( const char*, const char* )?  
    //  OR  
    // trying to convert str2 to T and then call  
    // T::operator<( const T& )?  
  
    if( str1 < str2 )   // C2666  
  
    if ( str1.operator < ( str2 ) )   // Treat str2 as type T  
        printf_s("str1.operator < ( str2 )\n");  
  
    if ( str1.operator char*() < str2 )   // Treat str1 as type char*  
        printf_s("str1.operator char*() < str2\n");  
}  
```  
  
## 예제  
 다음 샘플에서는 C2666 경고가 발생하는 경우를 보여 줍니다.  
  
```  
// C2666c.cpp  
// compile with: /c  
  
enum E   
{  
    E_A,   E_B  
};  
  
class A   
{  
    int h(const E e) const {return 0; }  
    int h(const int i) { return 1; }  
    // Uncomment the following line to resolve.  
    // int h(const E e) { return 0; }  
  
    void Test()   
    {  
        h(E_A);   // C2666  
        h((const int) E_A);  
        h((int) E_A);  
    }  
};  
```