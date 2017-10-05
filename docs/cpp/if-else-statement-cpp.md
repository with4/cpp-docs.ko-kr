---
title: "if-else 문 (c + +) | Microsoft Docs"
ms.custom: 
ms.date: 07/17/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- else_cpp
- else
- if_cpp
- if
dev_langs:
- C++
helpviewer_keywords:
- if keyword [C++]
- else keyword [C++]
- if keyword [C++], if-else
ms.assetid: f8c45cde-6bce-42ae-81db-426b3dbd4caa
caps.latest.revision: 13
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 7f6d2a553e34b5f15e53fa142241af83d8e91255
ms.contentlocale: ko-kr
ms.lasthandoff: 09/25/2017

---
# <a name="if-else-statement-c"></a>if-else 문 (C++)
조건부 분기를 제어 합니다. *if 블록* 경우에 실행 되는 *if 식을* 0이 아닌 값으로 계산 (또는 `true`). 하는 경우의 값 *식* 이 값은 0 *statement1* 및 블록의 다른 문이 실행 되 고 블록에서는 다른 있는 경우를 건너뜁니다. 하는 경우의 값 *식* 가 0 이면 다음 if 블록이 생략 되 고 다른-블록이 있는 경우 실행 됩니다. 0이 아닌 값을 평가 하는 식은
- `true`
- null이 아닌 포인터
- 0이 아닌 산술 값 또는 
- 클래스 형식으로 명확한 변환을 하는 산술, 부울 또는 포인터를 정의 하는 입력 합니다. (변환에 대 한 정보를 참조 하십시오. [표준 변환](../cpp/standard-conversions.md).)   
  
## <a name="syntax"></a>구문  
  
```  
  
if ( expression )  
{
   statement1;
   ...  
}
else  // optional
{
   statement2;
   ...
} 

// Visual Studio 2017 version 15.3 and later:
if ( initialization; expression )  
{
   statement1;
   ...  
}
else  // optional
{
   statement2;
   ...
}  

// Visual Studio 2017 version 15.3 and later:
if constexpr (expression)
{
    statement1;
    ...
}
else  // optional
{
   statement2;
   ...
} 
```  
## <a name="example"></a>예제  
```  
// if_else_statement.cpp  
#include <iostream>

using namespace std;

class C
{
    public:
    void do_somthing(){}
};
void init(C){}
bool is_true() { return true; }
int x = 10;

int main()
{
    if (is_true())
    {
        cout << "b is true!\n";  // executed
    }
    else
    {
        cout << "b is false!\n";
    }

  // no else statement
    if (x == 10)
    {
        x = 0; 
    }
    
  
    C* c;
  init(c);
    if (c)
    {
        c->do_something();
    }
    else
    {
        cout << "c is null!\n";
    }
}
```  
## <a name="if-statement-with-an-initializer"></a>경우는 이니셜라이저를 사용 하 여 문을
**Visual Studio 2017 15.3 이상 버전** (사용할 수 있는 [/std:c + + 17](../build/reference/std-specify-language-standard-version.md)):는 **경우** 문을 선언 하 고 명명된 된 변수를 초기화 하는 식을 포함 될 수도 있습니다. If 블록의 범위 내 변수만 필요한 경우 이러한 형태의 if 문을 사용 합니다. 

```cpp
## Example  
#include <iostream>
#include <mutex>
#include <map>
#include <string>
#include <algorithm>


using namespace std;

map<int, string> m;
mutex mx;
bool shared_flag; // guarded by mx
void unsafe_operation() {}

int main()
{

    if (auto it = m.find(10); it != m.end())
    {
        cout << it->second;
        return 0;
    }

    if (char buf[10]; fgets(buf, 10, stdin))
    {
        m[0] += buf;
    }

    if (lock_guard<mutex> lock(mx); shared_flag)
    {
        unsafe_operation();
        shared_flag = false;
    }


    string s{ "if" };
    if (auto keywords = { "if", "for", "while" }; any_of(keywords.begin(), keywords.end(), [&s](const char* kw) { return s == kw; }))
    {
        cout << "Error! Token must not be a keyword\n";
    }

}
```

 모든 양식에서에서 **경우** 문, *식*, 모든 파생 작업이 계산 되는 구조를 제외한 모든 값을 사용할 수 있는 합니다. 컨트롤에서 전달는 **경우** 문을 다음 문으로 프로그램에서 하지 않는 한 중 하나는 *문을*s에는 [나누기](../cpp/break-statement-cpp.md), [계속](../cpp/continue-statement-cpp.md), 또는 [goto](../cpp/goto-statement-cpp.md)합니다.  
  
 **다른** 절은 `if...else` 문은 가장 가까운와 연결 된 이전 **경우** 해당 하지 않은 동일한 범위에서 문을 **다른** 문입니다.   

## <a name="constexpr-if-statements"></a>constexpr 경우 문
**Visual Studio 2017 15.3 이상 버전** (사용할 수 있는 [/std:c + + 17](../build/reference/std-specify-language-standard-version.md)): 함수 템플릿을 사용할 수 있습니다는 **constexpr 경우** 문을 컴파일할 분기 결정을 내릴 수 함수 오버 로드를 여러 개에 의존 하지 않고도 합니다. 예를 들어 해당 핸들 매개 변수의 압축을 푼 (0이 매개 변수 오버 로드가 필요) 함수를 하나 작성할 수 있습니다. 

```cpp
template <class T, class... Rest>
void f(T&& t, Rest&&... r)
{
// handle t
   do_something(t);

   // handle r conditionally
   constexpr if (sizeof...(r)) 
   {
      
      f(r...); 
   }
   else
   {
       g(r...);
   }
}
```

  
 
## <a name="see-also"></a>참고 항목  
 [선택 문](../cpp/selection-statements-cpp.md)   
 [키워드](../cpp/keywords-cpp.md)   
 [switch 문(C++)](../cpp/switch-statement-cpp.md)
