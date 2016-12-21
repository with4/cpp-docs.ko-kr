---
title: "unary_negate 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "unary_negate"
  - "std::unary_negate"
  - "std.unary_negate"
  - "xfunctional/std::unary_negate"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "unary_negate 클래스"
ms.assetid: e3b86eec-3205-49b9-ab83-f55225af4e0c
caps.latest.revision: 21
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# unary_negate 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

지정된 단항 함수의 반환 값을 무효화하는 멤버 함수를 제공하는 템플릿 클래스.  
  
## 구문  
  
```  
  
   template<class Predicate>  
class unary_negate  
   : public unary_function<  
      typename Predicate::argument_type,  
      bool>   
{  
public:  
explicit unary_negate(  
   const Predicate& _Func  
);  
bool operator()(  
   const typename Predicate::argument_type& _Left ) const;  
};  
```  
  
#### 매개 변수  
 `_Func`  
 The unary function to be negated.  
  
 `_Left`  
 The operand of the unary function to be negated.  
  
## 반환 값  
 The negation of the unary function.  
  
## 설명  
 The template class stores a copy of a unary function object \_*Func.* It defines its member function `operator()` as returning **\!**\_*Func\(\_Left\).*  
  
 The constructor of `unary_negate` is rarely used directly.  The helper function [not1](../Topic/not1%20Function.md) provides an easier way to declare and use the **unary\_negator** adaptor predicate.  
  
## 예제  
  
```  
// functional_unary_negate.cpp  
// compile with: /EHsc  
#include <vector>  
#include <functional>  
#include <algorithm>  
#include <iostream>  
  
using namespace std;  
  
int main()  
{  
    vector<int> v1;  
    vector<int>::iterator Iter;  
  
    int i;  
    for (i = 0; i <= 7; i++)  
    {  
        v1.push_back(5 * i);  
    }  
  
    cout << "The vector v1 = ( ";  
    for (Iter = v1.begin(); Iter != v1.end(); Iter++)  
        cout << *Iter << " ";  
    cout << ")" << endl;  
  
    vector<int>::iterator::difference_type result1;  
    // Count the elements greater than 10  
    result1 = count_if(v1.begin(), v1.end(), bind2nd(greater<int>(), 10));  
    cout << "The number of elements in v1 greater than 10 is: "  
         << result1 << "." << endl;  
  
    vector<int>::iterator::difference_type result2;  
    // Use the negator to count the elements less than or equal to 10  
    result2 = count_if(v1.begin(), v1.end(),  
        unary_negate<binder2nd <greater<int> > >(bind2nd(greater<int>(),10)));  
  
    // The following helper function not1 also works for the above line  
    // not1(bind2nd(greater<int>(), 10)));  
  
    cout << "The number of elements in v1 not greater than 10 is: "  
         << result2 << "." << endl;  
}  
```  
  
  **The vector v1 \= \( 0 5 10 15 20 25 30 35 \)**  
**The number of elements in v1 greater than 10 is: 5.**  
**The number of elements in v1 not greater than 10 is: 3.**   
## 요구 사항  
 **헤더:** \<기능\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [표준 템플릿 라이브러리](../misc/standard-template-library.md)