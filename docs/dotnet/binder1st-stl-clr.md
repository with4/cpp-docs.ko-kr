---
title: "binder1st(STL/CLR) | Microsoft Docs"
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
  - "cliext::binder1st"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "binder1st 함수[STL/CLR]"
ms.assetid: a989c9cc-a485-45d9-bd19-519018e6974b
caps.latest.revision: 18
caps.handback.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# binder1st(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The template class describes a one\-argument functor that, when called, returns its stored two\-argument functor called with its stored first argument and the supplied second argument.  You use it specify a function object in terms of its stored functor.  
  
## 구문  
  
```  
template<typename Fun>  
    ref class binder1st  
    { // wrap operator()  
public:  
    typedef Fun stored_function_type;  
    typedef typename Fun::first_argument_type first_argument_type;  
    typedef typename Fun::second_argument_type second_argument_type;  
    typedef typename Fun:result_type result_type;  
    typedef Microsoft::VisualC::StlClr::UnaryDelegate<  
        second_argument_type, result_type>  
        delegate_type;  
  
    binder1st(Fun% functor, first_argument_type left);  
    binder1st(binder1st<Arg>% right);  
  
    result_type operator()(second_argument_type right);  
    operator delegate_type^();  
    };  
```  
  
#### 매개 변수  
 Fun  
 The type of the stored functor.  
  
## 멤버 함수  
  
|Type Definition|설명|  
|---------------------|--------|  
|delegate\_type|The type of the generic delegate.|  
|first\_argument\_type|The type of the functor first argument.|  
|result\_type|The type of the functor result.|  
|second\_argument\_type|The type of the functor second argument.|  
|stored\_function\_type|The type of the functor.|  
  
|멤버|설명|  
|--------|--------|  
|binder1st|Constructs the functor.|  
  
|연산자|설명|  
|---------|--------|  
|operator\(\)|Computes the desired function.|  
|operator delegate\_type^\(\)|Casts the functor to a delegate.|  
  
## 설명  
 The template class describes a one\-argument functor that stores a two\-argument functor and a first argument.  It defines the member operator `operator()` so that, when the object is called as a function, it returns the result of calling the stored functor with the stored first argument and the supplied second argument.  
  
 You can also pass the object as a function argument whose type is `delegate_type^` and it will be converted appropriately.  
  
## 예제  
  
```  
// cliext_binder1st.cpp   
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
    Myvector c3(2, 0);   
  
// display initial contents " 4 3"   
    for each (int elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display   
    cliext::minus<int> sub_op;   
    cliext::binder1st<cliext::minus<int> > subfrom3(sub_op, 3);   
  
    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),   
        subfrom3);   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display with function   
    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),   
        bind1st(sub_op, 3));   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **4 3**  
 **\-1 0**  
 **\-1 0**   
## 요구 사항  
 **Header:** \<cliext\/functional\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [bind1st](../dotnet/bind1st-stl-clr.md)