---
title: "함수 호출 연산자: () | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "( ) 함수 호출 연산자"
  - "() 함수 호출 연산자"
  - "함수 호출 연산자 ( )"
  - "함수 호출, C++ 함수"
  - "함수 호출, operator"
  - "함수[C++], 함수 호출 연산자"
  - "후위 연산자"
ms.assetid: 50c92e59-a4bf-415a-a6ab-d66c679ee80a
caps.latest.revision: 14
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 함수 호출 연산자: ()
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

후위 식 뒤에 함수 호출 연산자 **\( \)**가 오면 함수 호출이 지정됩니다.  
  
## 구문  
  
```  
  
postfix-expression   
( [argument-expression-list ] )  
```  
  
## 설명  
 함수 호출 연산자의 인수는 쉼표로 구분된 0개 이상의 식\(함수의 실제 인수\)입니다.  
  
 *postfix\-expression*은 함수 주소\(예: 함수 식별자 또는 함수 포인터의 값\)로 계산되어야 하고 *argument\-expression\-list*는 값\(인수\)이 함수로 전달되는 식 목록\(쉼표로 구분됨\)입니다.  *인수 식 목록* 인수는 비워둘 수 있습니다.  
  
 *postfix\-expression*은 다음 형식 중 하나여야 합니다.  
  
-   `T` 형식을 반환하는 함수.  선언 예제:  
  
    ```  
    T func( int i )  
    ```  
  
-   `T` 형식을 반환하는 함수의 포인터.  선언 예제:  
  
    ```  
    T (*func)( int i )  
    ```  
  
-   `T` 형식을 반환하는 함수의 참조.  선언 예제:  
  
    ```  
    T (&func)(int i)  
    ```  
  
-   `T` 형식을 반환하는 멤버 포인터 함수 역참조.  함수 호출 예제:  
  
    ```  
    (pObject->*pmf)();  
    (Object.*pmf)();  
    ```  
  
## 예제  
 다음 예제에서는 3개의 인수로 표준 라이브러리 함수 `strcat_s`를 호출합니다.  
  
```  
// expre_Function_Call_Operator.cpp  
// compile with: /EHsc  
  
#include <iostream>  
#include <string>  
  
// STL name space  
using namespace std;  
  
int main()  
{  
    enum  
    {  
        sizeOfBuffer = 20  
    };  
  
    char s1[ sizeOfBuffer ] = "Welcome to ";  
    char s2[ ] = "C++";  
  
    strcat_s( s1, sizeOfBuffer, s2 );  
  
    cout << s1 << endl;  
}  
```  
  
  **C\+\+ 시작**   
## 함수 호출 결과  
 함수가 참조 형식으로 선언되지 않은 경우 함수 호출은 r\-value로 평가됩니다.  참조가 있는 함수는 l\-values로 평가하고 대입문의 왼쪽에서 다음과 같이 사용될 수 있습니다.  
  
```  
// expre_Function_Call_Results.cpp  
// compile with: /EHsc  
#include <iostream>  
class Point  
{  
public:  
    // Define "accessor" functions as  
    // reference types.  
    unsigned& x() { return _x; }  
    unsigned& y() { return _y; }  
private:  
    unsigned _x;  
    unsigned _y;  
};  
  
using namespace std;  
int main()  
{  
    Point ThePoint;  
  
    ThePoint.x() = 7;           // Use x() as an l-value.  
    unsigned y = ThePoint.y();  // Use y() as an r-value.  
  
    // Use x() and y() as r-values.  
    cout << "x = " << ThePoint.x() << "\n"  
         << "y = " << ThePoint.y() << "\n";  
}  
```  
  
 앞의 코드는 `Point`x 및 *y* 좌표를 나타내는 전용 데이터 개체를 포함하는 *라는 클래스를 정의합니다.* 이러한 데이터 개체를 수정하고 해당 값을 검색해야 합니다.  이 프로그램은 이러한 클래스를 위한 여러 디자인 중 하나이며, `GetX`와 `SetX` 또는 `GetY`와 `SetY` 함수는 사용할 수 있는 디자인입니다.  
  
 클래스 형식, 클래스 형식에 대한 포인터 또는 클래스 형식에 대한 참조를 반환하는 함수는 멤버 선택 연산자에 대한 왼쪽 피연산자로 사용할 수 있습니다.  따라서 다음 코드를 사용할 수 있습니다.  
  
```  
// expre_Function_Results2.cpp  
class A {  
public:  
   A() {}  
   A(int i) {}  
   int SetA( int i ) {  
      return (I = i);  
   }  
  
   int GetA() {  
      return I;  
   }  
  
private:  
   int I;  
};  
  
A func1() {  
   A a = 0;  
   return a;  
}  
  
A* func2() {  
   A *a = new A();  
   return a;  
}  
  
A& func3() {  
   A *a = new A();  
   A &b = *a;  
   return b;  
}  
  
int main() {  
   int iResult = func1().GetA();  
   func2()->SetA( 3 );  
   func3().SetA( 7 );  
}  
```  
  
 함수를 재귀적으로 호출할 수 있습니다.  함수 선언에 대한 자세한 내용은 [함수 지정자](../misc/function-specifiers.md) 및 [멤버 함수](../misc/member-functions-cpp.md)를 참조하세요.  관련 자료는 [프로그램 및 링크](../cpp/program-and-linkage-cpp.md)에 있습니다.  
  
## 참고 항목  
 [후위 식](../cpp/postfix-expressions.md)   
 [C\+\+ 연산자](../misc/cpp-operators.md)   
 [C\+\+ 연산자, 우선 순위 및 결합성](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [함수 호출](../c-language/function-call-c.md)   
 [\(NOTINBUILD\) Function Declarations](http://msdn.microsoft.com/ko-kr/3f9b4e14-60d2-47c1-acd8-4fa8fc988be7)