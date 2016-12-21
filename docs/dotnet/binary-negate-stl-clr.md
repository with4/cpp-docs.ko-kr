---
title: "binary_negate(STL/CLR) | Microsoft Docs"
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
  - "cliext::binary_negate"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "binary_negate 함수[STL/CLR]"
ms.assetid: 0c3b47eb-0f37-4cb2-b879-4c9f0e57d275
caps.latest.revision: 16
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# binary_negate(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

템플릿 클래스는 호출될 때 함수를 설명하고 저장된 두 인수 함수의 논리적 NOT 을 반환합니다.  저장된 함수에서 함수 개체를 지정할 때 사용합니다.  
  
## 구문  
  
```  
template<typename Fun>  
    ref class binary_negate  
    { // wrap operator()  
public:  
    typedef Fun stored_function_type;  
    typedef typename Fun::first_argument_type first_argument_type;  
    typedef typename Fun::second_argument_type second_argument_type;  
    typedef bool result_type;  
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<  
        first_argument_type, second_argument_type, result_type>  
        delegate_type;  
  
    explicit binary_negate(Fun% functor);  
    binary_negate(binary_negate<Arg>% right);  
  
    result_type operator()(first_argument_type left,  
        second_argument_type right);  
    operator delegate_type^();  
    };  
```  
  
#### 매개 변수  
 Fun  
 저장 된 함수의 형식입니다.  
  
## 멤버 함수  
  
|형식 정의|설명|  
|-----------|--------|  
|대리자 형식|일반적 대리자의 형식입니다.|  
|첫 번째 인수 형식입니다.|함수 첫 번째 인수의 형식입니다.|  
|결과 형식|함수 결과의 형식입니다.|  
|두 번째 인수 형식입니다.|함수 둘째 인수의 형식입니다.|  
|저장된 함수 형식|함수의 형식입니다.|  
  
|멤버|설명|  
|--------|--------|  
|binary\_negate|함수를 생성합니다.|  
  
|연산자|설명|  
|---------|--------|  
|operator\(\)|원하는 함수를 계산합니다.|  
|operator delegate\_type^\(\)|대리자에 함수를 캐스팅합니다.|  
  
## 설명  
 템플릿 클래스는 다른 두 인수를 저장하는 두 인수 함수를 설명합니다.  개체가 함수로 호출되었을 때 멤버 연산자 `operator()` 를 정의함으로서 두 인수를 사용하여 호출된 저장된 함수의 논리적 NOT을 반환합니다.  
  
 형식이 `delegate_type^` 인 개체는 함수 인수로 전달할 수 있고 적절하게 변환됩니다.  
  
## 예제  
  
```  
// cliext_binary_negate.cpp   
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
    cliext::less<int> less_op;   
  
    cliext::transform(c1.begin(), c1.begin() + 2,   
        c2.begin(), c3.begin(),   
        cliext::binary_negate<cliext::less<int> >(less_op));   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display with function   
    cliext::transform(c1.begin(), c1.begin() + 2,   
        c2.begin(), c3.begin(), cliext::not2(less_op));   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **4 3**  
 **4 4**  
 **1 0**  
 **1 0**   
## 요구 사항  
 \`**Header:** \<cliext\/functional\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [not2](../dotnet/not2-stl-clr.md)