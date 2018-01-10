---
title: "컴파일러 오류 C2666 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2666
dev_langs: C++
helpviewer_keywords: C2666
ms.assetid: 78364d15-c6eb-439a-9088-e04a0176692b
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1542eb409c77e8a9919f1884a59810e587d11f11
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2666"></a>컴파일러 오류 C2666
'identifier': 숫자 오버 로드에 비슷한 변환이  
  
 오버 로드 된 함수 또는 연산자가 모호 합니다.   형식 매개 변수 목록이 모호성을 해결 하려면 컴파일러에 대 한 너무 유사할 수 있습니다.  이 오류를 해결 하려면 하나 이상의 실제 매개 변수를 명시적으로 캐스팅 합니다.  
  
 다음 샘플에서는 C2666 오류가 생성 됩니다.  
  
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
  
 이 오류는 Visual Studio.NET 2003에 대해 수행한 컴파일러 규칙 작업의 결과로 생성 수 있습니다.  
  
-   이항 연산자 및 포인터 형식으로 사용자 정의 변환  
  
-   한정 변환 동일 변환 동일 하지 않습니다.  
  
 이항 연산자에 대 한 \<, >, \<=, 및 > =는 전달 된 매개 변수는 이제 암시적으로 변환 피연산자의 형식 매개 변수의 형식 피연산자의 형식으로 변환 하는 사용자 정의 변환 연산자를 정의 하는 경우. 잠재적으로 모호성에 대 한 합니다.  
  
 Visual Studio.NET 2003 및 Visual c + +의 Visual Studio.NET 버전 둘 다에 적용 되는 코드를 명시적으로 함수 구문을 사용 하 여 클래스 연산자를 호출 합니다.  
  
## <a name="example"></a>예  
  
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
  
    // Error - Ambiguous call to operator<()  
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
  
## <a name="example"></a>예  
 다음 샘플에서는 C2666  
  
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