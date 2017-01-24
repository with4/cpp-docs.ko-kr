---
title: "not_equal_to(STL/CLR) | Microsoft Docs"
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
  - "cliext::not_equal_to"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "not_equal_to 함수[STL/CLR]"
ms.assetid: 1b66e0ca-eace-4672-8da9-ed16f8608bca
caps.latest.revision: 16
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# not_equal_to(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

만일 첫번째 인수가 두번째와 동일하지 않은 경우, 템플릿 클래스는 함수 설명하고, 호출할 때 true 반환합니다.  인수 형식에서 함수 개체를 지정할 때 사용합니다.  
  
## 구문  
  
```  
template<typename Arg>  
    ref class not_equal_to  
    { // wrap operator()  
public:  
    typedef Arg first_argument_type;  
    typedef Arg second_argument_type;  
    typedef bool result_type;  
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<  
        first_argument_type, second_argument_type, result_type>  
        delegate_type;  
  
    not_equal_to();  
    not_equal_to(not_equal_to<Arg>% right);  
  
    result_type operator()(first_argument_type left,  
        second_argument_type right);  
    operator delegate_type^();  
    };  
```  
  
#### 매개 변수  
 Arg  
 인수의 형식입니다.  
  
## 멤버 함수  
  
|형식 정의|설명|  
|-----------|--------|  
|대리자 형식|일반적 대리자의 형식입니다.|  
|첫 번째 인수 형식입니다.|함수 첫 번째 인수의 형식입니다.|  
|결과 형식|함수 결과의 형식입니다.|  
|두 번째 인수 형식입니다.|함수 둘째 인수의 형식입니다.|  
  
|멤버|설명|  
|--------|--------|  
|not\_equal\_to|함수를 생성합니다.|  
  
|연산자|설명|  
|---------|--------|  
|operator\(\)|원하는 함수를 계산합니다.|  
|operator delegate\_type^|대리자에 함수를 캐스팅합니다.|  
  
## 설명  
 템플릿 클래스는 두 인수를 가지는 함수를 설명합니다.  멤버 연산자 `operator()` 를 정의하도록 개체가 함수로써 호출하고, 만일 첫번째 인수가 두번째와 동일하지 않은 경우 오직 true를 반환합니다.  
  
 형식이 `delegate_type^` 인 개체는 함수 인수로 전달할 수 있고 적절하게 변환됩니다.  
  
## 예제  
  
```  
// cliext_not_equal_to.cpp   
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
        c2.begin(), c3.begin(), cliext::not_equal_to<int>());   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **4 3**  
 **4 4**  
 **0 1**   
## 요구 사항  
 \`**Header:** \<cliext\/functional\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [equal\_to](../dotnet/equal-to-stl-clr.md)