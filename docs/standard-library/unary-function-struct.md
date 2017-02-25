---
title: "unary_function 구조체 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.unary_function"
  - "unary_function"
  - "functional/std::unary_function"
  - "std::unary_function"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "unary_function 클래스"
ms.assetid: 04c2fbdc-c1f6-48ed-b6cc-292a6d484627
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# unary_function 구조체
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

An empty base struct that defines types that may be inherited by derived classes that provides a unary function object.  
  
## 구문  
  
```  
  
   template<class Arg, class Result>  
struct unary_function {  
   typedef Arg argument_type;  
   typedef Result result_type;  
};  
```  
  
## 설명  
 The template struct serves as a base for classes that define a member function of the form **result\_type** `operator()`\(**const argument\_type&**\) **const**.  
  
 All such derived unary functions can refer to their sole argument type as **argument\_type** and their return type as **result\_type**.  
  
## 예제  
  
```  
// functional_unary_function.cpp  
// compile with: /EHsc  
#include <vector>  
#include <functional>  
#include <algorithm>  
#include <iostream>  
  
using namespace std;  
  
// Creation of a user-defined function object  
// that inherits from the unary_function base class  
class greaterthan10: unary_function<int, bool>  
{  
public:  
    result_type operator()(argument_type i)  
    {  
        return (result_type)(i > 10);  
    }  
};  
  
int main()  
{  
    vector<int> v1;  
    vector<int>::iterator Iter;  
  
    int i;  
    for (i = 0; i <= 5; i++)  
    {  
        v1.push_back(5 * i);  
    }  
  
    cout << "The vector v1 = ( " ;  
    for (Iter = v1.begin(); Iter != v1.end(); Iter++)  
        cout << *Iter << " ";  
    cout << ")" << endl;  
  
    vector<int>::iterator::difference_type result1;  
    result1 = count_if(v1.begin(), v1.end(), greaterthan10());  
    cout << "The number of elements in v1 greater than 10 is: "  
         << result1 << "." << endl;  
}  
```  
  
  **벡터 v1 \= \(0 5 10 15 20 25\)**  
**The number of elements in v1 greater than 10 is: 3.**   
## 요구 사항  
 **헤더:** \<기능\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [unary\_function\<\> 구조체](../misc/unary-function-angles-structure.md)   
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [표준 템플릿 라이브러리](../misc/standard-template-library.md)