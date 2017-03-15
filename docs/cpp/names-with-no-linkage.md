---
title: "링크가 없는 이름 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "열거자[C++], 링크"
  - "함수 매개 변수[C++]"
  - "함수[C++], 매개 변수"
  - "이름[C++], 링크가 없는"
  - "형식 정의 이름, 링크"
ms.assetid: 7174c500-12d2-4572-8c16-63c27c758fb1
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# 링크가 없는 이름
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

링크가 없는 유일한 이름은 다음과 같습니다.  
  
-   함수 매개 변수  
  
-   `extern` 또는 **static**으로 선언되지 않는 블록 범위 이름입니다.  
  
-   열거자  
  
-   `typedef` 문에 선언된 이름입니다.  한 가지 예외는 `typedef` 문을 사용하여 명명되지 않은 클래스 형식의 이름을 제공할 때입니다.  클래스에 외부 링크가 있으면 이름에 외부 링크가 있을 수 있습니다.  다음 예제에서는 `typedef` 이름에 외부 링크가 있는 경우를 보여 줍니다.  
  
    ```  
    // names_with_no_linkage.cpp  
    typedef struct  
    {  
       short x;  
       short y;  
    } POINT;  
  
    extern int MoveTo( POINT pt );  
  
    int main()  
    {  
    }  
    ```  
  
     `typedef` 이름인 `POINT`는 이름이 지정되지 않은 구조체의 클래스 이름이 됩니다.  그런 다음 이 이름은 외부 링크로 함수를 선언하는 데 사용됩니다.  
  
 `typedef` 이름에 링크가 없기 때문에 해당 정의는 변환 단위 간에 다를 수 있습니다.  컴파일은 개별적으로 수행되기 때문에 컴파일러가 이러한 차이를 감지할 수 없습니다.  따라서 이러한 종류의 오류는 링크 타임까지 검색되지 않습니다.  다음 경우를 참조하세요.  
  
```  
// Translation unit 1  
typedef int INT  
  
INT myInt;  
...  
  
// Translation unit 2  
typedef short INT  
  
extern INT myInt;  
...  
```  
  
 앞의 코드에서 링크 타임에 "확인되지 않은 외부" 오류를 생성합니다.  
  
## 예제  
 C\+\+ 함수는 파일 또는 클래스 범위에서만 정의할 수 있습니다.  다음 예제에서는 함수를 정의하는 방법 및 잘못된 함수 정의를 보여 줍니다.  
  
```  
// function_definitions.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
void ShowChar( char ch );    // Declare function ShowChar.  
  
void ShowChar( char ch )     // Define function ShowChar.  
{                            // Function has file scope.  
   cout << ch;  
}  
  
struct Char                  // Define class Char.  
{  
    char Show();             // Declare Show function.  
    char Get();              // Declare Get function.  
    char ch;  
};  
  
char Char::Show()            // Define Show function  
{                            //  with class scope.  
    cout << ch;  
    return ch;  
}  
  
void GoodFuncDef( char ch )  // Define GoodFuncDef  
{                            //  with file scope.  
    int BadFuncDef( int i )  // C2601, Erroneous attempt to  
    {                        //  nest functions.  
        return i * 7;  
    }  
    for( int i = 0; i < BadFuncDef( 2 ); ++i )  
        cout << ch;  
    cout << "\n";  
}  
```  
  
## 참고 항목  
 [프로그램 및 링크](../cpp/program-and-linkage-cpp.md)