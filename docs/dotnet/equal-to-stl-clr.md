---
title: "equal_to(STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::equal_to"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "equal_to 함수[STL/CLR]"
ms.assetid: 9dd6e27d-e695-470f-b7a7-19a6db970ee5
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 16
---
# equal_to(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The template class describes a functor that, when called, returns true only if the first argument is equal to the second.  You use it specify a function object in terms of its argument type.  
  
## 구문  
  
```  
template<typename Arg>  
    ref class equal_to  
    { // wrap operator()  
public:  
    typedef Arg first_argument_type;  
    typedef Arg second_argument_type;  
    typedef bool result_type;  
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<  
        first_argument_type, second_argument_type, result_type>  
        delegate_type;  
  
    equal_to();  
    equal_to(equal_to<Arg>% right);  
  
    result_type operator()(first_argument_type left,  
        second_argument_type right);  
    operator delegate_type^();  
    };  
```  
  
#### 매개 변수  
 Arg  
 The type of the arguments.  
  
## 멤버 함수  
  
|Type Definition|설명|  
|---------------------|--------|  
|delegate\_type|The type of the generic delegate.|  
|first\_argument\_type|The type of the functor first argument.|  
|result\_type|The type of the functor result.|  
|second\_argument\_type|The type of the functor second argument.|  
  
|멤버|설명|  
|--------|--------|  
|equal\_to|Constructs the functor.|  
  
|연산자|설명|  
|---------|--------|  
|operator\(\)|Computes the desired function.|  
|operator delegate\_type^\(\)|Casts the functor to a delegate.|  
  
## 설명  
 The template class describes a two\-argument functor.  It defines the member operator `operator()` so that, when the object is called as a function, it returns true only if the first argument is equal to the second.  
  
 You can also pass the object as a function argument whose type is `delegate_type^` and it will be converted appropriately.  
  
## 예제  
  
```  
// cliext_equal_to.cpp   
// compile with: /clr   
#include <cliext/algorithm>   
#include <cliext/functional>   
#include <cliext/vector>   
  
typedef cliext::vector<int> Myvector;   
int main()   
    {   
    Myvector c1;   
    c1.push_back(4);   
    c1.push_back(3);   
    Myvector c2;   
    c2.push_back(4);   
    c2.push_back(4);   
    Myvector c3(2, 0);   
  
// display initial contents " 4 3" and " 4 4"   
    for each (int elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    for each (int elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display   
    cliext::transform(c1.begin(), c1.begin() + 2,   
        c2.begin(), c3.begin(), cliext::equal_to<int>());   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **4 3**  
 **4 4**  
 **1 0**   
## 요구 사항  
 **Header:** \<cliext\/functional\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [not\_equal\_to](../dotnet/not-equal-to-stl-clr.md)