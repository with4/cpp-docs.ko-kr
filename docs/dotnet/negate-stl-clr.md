---
title: "negate(STL/CLR) | Microsoft Docs"
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
  - "cliext::negate"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "negate 함수[STL/CLR]"
ms.assetid: 58e4c339-0dee-4db8-b2cc-de8920977039
caps.latest.revision: 18
caps.handback.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# negate(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The template class describes a functor that, when called, returns its argument negated.  You use it specify a function object in terms of its argument type.  
  
## 구문  
  
```  
template<typename Arg>  
    ref class negate  
    { // wrap operator()  
public:  
    typedef Arg argument_type;  
    typedef bool result_type;  
    typedef Microsoft::VisualC::StlClr::UnaryDelegate<  
        argument_type, result_type>  
        delegate_type;  
  
    negate();  
    negate(negate<Arg>% right);  
  
    result_type operator()(argument_type left);  
    operator delegate_type^();  
    };  
```  
  
#### 매개 변수  
 Arg  
 The type of the arguments.  
  
## 멤버 함수  
  
|Type Definition|설명|  
|---------------------|--------|  
|argument\_type|The type of the functor argument.|  
|delegate\_type|The type of the generic delegate.|  
|result\_type|The type of the functor result.|  
  
|멤버|설명|  
|--------|--------|  
|negate|Constructs the functor.|  
  
|연산자|설명|  
|---------|--------|  
|operator\(\)|Computes the desired function.|  
|operator delegate\_type^|Casts the functor to a delegate.|  
  
## 설명  
 The template class describes a one\-argument functor.  It defines the member operator `operator()` so that, when the object is called as a function, it returns its argument negated.  
  
 You can also pass the object as a function argument whose type is `delegate_type^` and it will be converted appropriately.  
  
## 예제  
  
```  
// cliext_negate.cpp   
// compile with: /clr   
#include <cliext/algorithm>   
#include <cliext/functional>   
#include <cliext/vector>   
  
typedef cliext::vector<int> Myvector;   
int main()   
    {   
    Myvector c1;   
    c1.push_back(4);   
    c1.push_back(-3);   
    Myvector c3(2, 0);   
  
// display initial contents " 4 -3"   
    for each (int elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display   
    cliext::transform(c1.begin(), c1.begin() + 2,   
        c3.begin(), cliext::negate<int>());   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **4 \-3**  
 **\-4 3**   
## 요구 사항  
 **Header:** \<cliext\/functional\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [logical\_not](../dotnet/logical-not-stl-clr.md)