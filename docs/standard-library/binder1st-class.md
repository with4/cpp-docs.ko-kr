---
title: "binder1st 클래스 | Microsoft Docs"
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
  - "xfunctional/std::binder1st"
  - "std::binder1st"
  - "binder1st"
  - "std.binder1st"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "binder1st 클래스"
ms.assetid: 6b8ee343-c82f-48f8-867d-06f9d1d324c0
caps.latest.revision: 22
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# binder1st 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이항 함수의 첫 번째 인수에 지정된 값을 결합하여 이항 함수 개체를 단항 함수 개체로 변환하는 생성자를 제공하는 템플릿 클래스  
  
## 구문  
  
```  
template<class Operation>  
class binder1st  
   : public unary_function <  
      typename Operation::second_argument_type,  
      typename Operation::result_type>   
  {  
   public:  
   typedef typename Operation::argument_type argument_type;  
   typedef typename Operation::result_type result_type;  
   binder1st(  
      const Operation & _Func,  
      const typename Operation::first_argument_type& _Left  
   );  
   result_type operator()(  
      const argument_type& _Right  
   ) const;  
   result_type operator()(  
      const argument_type& _Right  
   ) const;  
   protected:  
   Operation op;  
   typename Operation::first_argument_type value;  
   };  
```  
  
#### 매개 변수  
 `_Func`  
 The binary function object to be converted to a unary function object.  
  
 `_Left`  
 The value to which the first argument of the binary function object is to be bound.  
  
 `_Right`  
 The value of the argument that the adapted binary object compares to the fixed value of the second argument.  
  
## 반환 값  
 The unary function object that results from binding the first argument of the binary function object to the value `_Left.`  
  
## 설명  
 The template class stores a copy of a binary function object `_Func` in **op**, and a copy of `_Left` in **value**.  It defines its member function `operator()` as returning **op**\(**value**, `_Right`\).  
  
 If `_Func` is an object of type **Operation** and `c` is a constant , then [bind1st](../Topic/bind1st%20Function.md) \( `_Func`, `c` \) is equivalent to the `binder1st` class constructor `binder1st`\<**Operation**\> \( `_Func`, `c` \) and more convenient.  
  
## 예제  
  
```  
// functional_binder1st.cpp  
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
    for (i = 0; i <= 5; i++)  
    {  
        v1.push_back(5 * i);  
    }  
  
    cout << "The vector v1 = ( ";  
    for (Iter = v1.begin(); Iter != v1.end(); Iter++)  
        cout << *Iter << " ";  
    cout << ")" << endl;  
  
    // Count the number of integers > 10 in the vector  
    vector<int>::iterator::difference_type result1;  
    result1 = count_if(v1.begin(), v1.end(),  
        binder1st<less<int> >(less<int>(), 10));  
    cout << "The number of elements in v1 greater than 10 is: "  
         << result1 << "." << endl;  
  
    // Compare use of binder2nd fixing 2nd argument:  
    // count the number of integers < 10 in the vector  
    vector<int>::iterator::difference_type result2;  
    result2 = count_if(v1.begin(), v1.end(),  
        binder2nd<less<int> >(less<int>(), 10));  
    cout << "The number of elements in v1 less than 10 is: "  
         << result2 << "." << endl;  
}  
```  
  
  **벡터 v1 \= \(0 5 10 15 20 25\)**  
**The number of elements in v1 greater than 10 is: 3.**  
**The number of elements in v1 less than 10 is: 2.**   
## 요구 사항  
 **헤더:** \<기능\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [표준 템플릿 라이브러리](../misc/standard-template-library.md)