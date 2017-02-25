---
title: "컴파일러 오류 C2143 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2143"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2143"
ms.assetid: 1d8d1456-e031-4965-9240-09a6e33ba81c
caps.latest.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 23
---
# 컴파일러 오류 C2143
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

구문 오류 : 'token1'이\(가\) 'token2' 앞에 없습니다.  
  
 컴파일러가 기대한 특정 토큰\(공백이 아닌 언어 요소\)과는 다른 토큰이 발견되었습니다.  
  
 함수 시도 블록을 사용할 경우 발생할 수 있는 이 오류에 대한 내용은 기술 자료 문서 [Knowledge Base article 241706](http://support.microsoft.com/kb/241706)을 참조하십시오.  
  
 [C\+\+ 언어 참조](../../cpp/cpp-language-reference.md)를 검사하여 코드 구문이 잘못된 부분을 확인합니다.  컴파일러는 문제를 발생시킨 줄을 발견한 이후에 이 오류를 보고할 수도 있으므로 오류 줄보다 앞에 있는 여러 코드 줄을 검사하십시오.  
  
 C2143 오류는 서로 다른 상황에서 발생할 수 있습니다.  
  
 운영자 이름을 정규화 할 수 있는 경우에 발생할 수 있습니다 \(`::`,  `->` , 및  `.` \) 키워드 다음에 야  `template` , 같이 있습니다.  
  
```cpp  
class MyClass  
{  
    template<class Ty, typename PropTy>  
    struct PutFuncType : public Ty::PutFuncType<Ty, PropTy> // error C2143  
    {  
    };  
};  
  
```  
  
 기본적으로 c \+ \+는  `Ty::PutFuncType`  쓸것이라고 가정합니다. 따라서 다음  `<`  으로 해석\-보다 작다.  알려야 컴파일러는 명시적으로  `PutFuncType`  는 꺾쇠 괄호 올바르게 구문 분석할 수 있도록 서식 파일입니다.  이 오류를 해결 하려면 사용 하는  `template`  종속 형식 이름을 다음과 같이 키워드입니다.  
  
```cpp  
class MyClass  
{  
    template<class Ty, typename PropTy>  
    struct PutFuncType : public Ty::template PutFuncType<Ty, PropTy> // correct  
    {  
    };  
};  
  
```  
  
 C2143는 **\/clr**을 사용할 때 `using` 지시문에 구문 오류가 있을 수 있습니다.  
  
```cpp  
// C2143a.cpp  
// compile with: /clr /c  
using namespace System.Reflection;   // C2143  
using namespace System::Reflection;  
```  
  
 **\/clr**을 사용하지 않고 CLR 구문을 사용하여 소스 코드 파일을 컴파일할 때 일어날 수도 있습니다.  
  
```cpp  
// C2143b.cpp  
ref struct A {   // C2143 error compile with /clr  
   void Test() {}  
};  
  
int main() {  
   A a;  
   a.Test();  
}  
```  
  
 `if` 문 다음에 오는 첫 번째 비공백 문자는 왼쪽 괄호여야 합니다.  컴파일러는 그 외의 어떠한 것도 변환할 수 없습니다.  
  
```cpp  
// C2143c.cpp  
int main() {  
   int j = 0;  
  
   // OK  
   if (j < 25)  
      ;  
  
   if (j < 25)   // C2143  
}  
```  
  
 C2143오류가 발견된 줄이나 오류가 있는 줄의 바로 윗줄 중 하나에 닫는 중괄호, 괄호 또는 세미콜론이 없습니다.  
  
```caml  
// C2143d.cpp  
// compile with: /c  
class X {  
   int member1;  
   int member2   // C2143  
} x;  
```  
  
 또는 클래스 선언에 잘못 된 태그가 없는 경우:  
  
```cpp  
// C2143e.cpp  
class X {  
   int member;  
} x;  
  
class + {};   // C2143 + is an invalid tag name  
class ValidName {};   // OK  
```  
  
 레이블이 문에 첨부되지 않았습니다.  예를 들어 복합 문 끝에 레이블을 단독으로 배치해야 하는 경우에는 이 레이블을 null 문에 첨부하십시오.  
  
```cpp  
// C2143f.cpp  
// compile with: /c  
void func1() {  
   // OK  
   end1:  
      ;  
  
   end2:   // C2143  
}  
```  
  
 표준 c \+ \+ 라이브러리의 형식에는 조건이 지정 되지 않은 호출이 수행 될 때 오류가 발생할 수 있습니다.  
  
```cpp  
// C2143g.cpp  
// compile with: /EHsc /c  
#include <vector>  
static vector<char> bad;   // C2143  
static std::vector<char> good;   // OK  
```  
  
 누락 된 또는  `typename`  키워드가 있습니다.  
  
```cpp  
// C2143h.cpp  
template <typename T>  
struct X {  
   struct Y {  
      int i;  
   };  
   Y memFunc();  
};  
template <typename T>  
X<T>::Y X<T>::memFunc() {   // C2143  
// try the following line instead  
// typename X<T>::Y X<T>::memFunc() {  
   return Y();  
}  
```  
  
 명시적 인스턴스화를 정의하려고 했습니다.  
  
```cpp  
// C2143i.cpp  
// compile with: /EHsc /c  
// template definition  
template <class T>  
void PrintType(T i, T j) {}  
  
template void PrintType(float i, float j){}   // C2143  
template void PrintType(float i, float j);   // OK  
```  
  
 C 프로그램에서는 함수의 시작 부분에 변수를 선언해야 하며, 함수가 비선언 명령을 실행한 후에는 변수를 선언할 수 없습니다.  
  
```c  
// C2143j.c  
int main()   
{  
    int i = 0;  
    i++;  
    int j = 0; // C2143  
}  
  
```