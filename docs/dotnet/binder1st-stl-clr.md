---
title: binder1st (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::binder1st
dev_langs:
- C++
helpviewer_keywords:
- binder1st function [STL/CLR]
ms.assetid: a989c9cc-a485-45d9-bd19-519018e6974b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 550340bad45c6a71a633f7924afdd0eaf775005f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="binder1st-stlclr"></a>binder1st(STL/CLR)
인수가 한 개인 함수를 설명 하는 템플릿 클래스는를 호출할 때는 저장된 첫 번째 인수 및 제공 된 두 번째 인수를 사용 하 여 호출 해당 저장된 인수가 두 개인 함수를 반환 합니다. 사용 하면 해당 저장된 함수 측면에서 함수 개체를 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
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
  
#### <a name="parameters"></a>매개 변수  
 재미  
 저장 된 함수의 형식입니다.  
  
## <a name="member-functions"></a>멤버 함수  
  
|형식 정의|설명|  
|---------------------|-----------------|  
|delegate_type|제네릭 대리자의 형식입니다.|  
|first_argument_type|구조 함수의 첫 번째 인수의 형식입니다.|  
|result_type|함수 결과의 형식입니다.|  
|second_argument_type|두 번째 함수 인수 형식입니다.|  
|stored_function_type|함수의 형식입니다.|  
  
|멤버|설명|  
|------------|-----------------|  
|binder1st|함수를 생성합니다.|  
  
|연산자|설명|  
|--------------|-----------------|  
|operator()|원하는 함수를 계산합니다.|  
|연산자 delegate_type^()|대리자에 함수를 캐스팅합니다.|  
  
## <a name="remarks"></a>설명  
 인수가 두 개인 함수 및 첫 번째 인수를 저장 하는 단일 인수 함수를 설명 하는 템플릿 클래스입니다. 멤버 연산자 정의 `operator()` 저장 첫 번째 인수와 제공 된 두 번째 인수 저장된 함수를 호출의 결과 반환 개체를 함수로 호출 될 때 되도록 합니다.  
  
 함수 인수는 형식의 개체를 전달할 수도 있습니다 `delegate_type^` 적절 하 게 변환 됩니다.  
  
## <a name="example"></a>예  
  
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
  
```Output  
4 3  
-1 0  
-1 0  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/기능 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [bind1st(STL/CLR)](../dotnet/bind1st-stl-clr.md)