---
title: "multiplies(STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::multiplies"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "곱하기 함수[STL/CLR]"
ms.assetid: 76d23149-789a-48a1-89f8-9103df82a1df
caps.latest.revision: 18
caps.handback.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# multiplies(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The template class describes a functor that, when called, returns the first argument times the second.  You use it specify a function object in terms of its argument type.  
  
## 구문  
  
```  
template<typename Arg>  
    ref class multiplies  
    { // wrap operator()  
public:  
    typedef Arg first_argument_type;  
    typedef Arg second_argument_type;  
    typedef Arg result_type;  
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<  
        first_argument_type, second_argument_type, result_type>  
        delegate_type;  
  
    multiplies();  
    multiplies(multiplies<Arg>% right);  
  
    result_type operator()(first_argument_type left,  
        second_argument_type right);  
    operator delegate_type^();  
    };  
```  
  
#### 매개 변수  
 Arg  
 The type of the arguments and return value.  
  
## 멤버 함수  
  
|Type Definition|설명|  
|---------------------|--------|  
|delegate\_type|The type of the generic delegate.|  
|first\_argument\_type|The type of the functor first argument.|  
|result\_type|The type of the functor result.|  
|second\_argument\_type|The type of the functor second argument.|  
  
|멤버|설명|  
|--------|--------|  
|multiplies|Constructs the functor.|  
  
|연산자|설명|  
|---------|--------|  
|operator\(\)|Computes the desired function.|  
|operator delegate\_type^|Casts the functor to a delegate.|  
  
## 설명  
 The template class describes a two\-argument functor.  It defines the member operator `operator()` so that, when the object is called as a function, it returns the first argument times the second.  
  
 You can also pass the object as a function argument whose type is `delegate_type^` and it will be converted appropriately.  
  
## 예제  
  
```  
// cliext_multiplies.cpp   
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
    c2.push_back(2);   
    c2.push_back(1);   
    Myvector c3(2, 0);   
  
// display initial contents " 4 3" and " 2 1"   
    for each (int elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    for each (int elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display   
    cliext::transform(c1.begin(), c1.begin() + 2,   
        c2.begin(), c3.begin(), cliext::multiplies<int>());   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **4 3**  
 **2 1**  
 **8 3**   
## 요구 사항  
 **Header:** \<cliext\/functional\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [divides](../dotnet/divides-stl-clr.md)   
 [나머지](../dotnet/modulus-stl-clr.md)