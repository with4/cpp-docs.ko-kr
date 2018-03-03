---
title: less_equal (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::less_equal
dev_langs:
- C++
helpviewer_keywords:
- less_equal function [STL/CLR]
ms.assetid: 87d5bebc-6e5a-4d70-b15c-7260d06d50f0
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: f0ecc202e1a83f0f32b0febef488bb1979cccb86
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="lessequal-stlclr"></a>less_equal(STL/CLR)
함수를 설명 하는 템플릿 클래스는 호출 되 면 true를 반환만 첫 번째 인수는 두 번째 보다 작거나 같은 경우입니다. 사용 하면 해당 인수 형식 기준으로 함수 개체를 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
template<typename Arg>  
    ref class less_equal  
    { // wrap operator()  
public:  
    typedef Arg first_argument_type;  
    typedef Arg second_argument_type;  
    typedef bool result_type;  
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<  
        first_argument_type, second_argument_type, result_type>  
        delegate_type;  
  
    less_equal();  
    less_equal(less_equal<Arg>% right);  
  
    result_type operator()(first_argument_type left,  
        second_argument_type right);  
    operator delegate_type^();  
    };  
```  
  
#### <a name="parameters"></a>매개 변수  
 Arg  
 형식 인수입니다.  
  
## <a name="member-functions"></a>멤버 함수  
  
|형식 정의|설명|  
|---------------------|-----------------|  
|delegate_type|제네릭 대리자의 형식입니다.|  
|first_argument_type|구조 함수의 첫 번째 인수의 형식입니다.|  
|result_type|함수 결과의 형식입니다.|  
|second_argument_type|두 번째 함수 인수 형식입니다.|  
  
|멤버|설명|  
|------------|-----------------|  
|less_equal|함수를 생성합니다.|  
  
|연산자|설명|  
|--------------|-----------------|  
|operator()|원하는 함수를 계산합니다.|  
|연산자 delegate_type ^|대리자에 함수를 캐스팅합니다.|  
  
## <a name="remarks"></a>설명  
 두 인수 함수를 설명 하는 템플릿 클래스입니다. 멤버 연산자 정의 `operator()` 개체 함수로 호출 될 때 있도록 true를 반환 하는지만 첫 번째 인수는 두 번째 보다 작거나 같은 경우입니다.  
  
 함수 인수는 형식의 개체를 전달할 수도 있습니다 `delegate_type^` 적절 하 게 변환 됩니다.  
  
## <a name="example"></a>예  
  
```  
// cliext_less_equal.cpp   
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
    c2.push_back(3);   
    c2.push_back(3);   
    Myvector c3(2, 0);   
  
// display initial contents " 4 3" and " 3 3"   
    for each (int elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    for each (int elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display   
    cliext::transform(c1.begin(), c1.begin() + 2,   
        c2.begin(), c3.begin(), cliext::less_equal<int>());   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
4 3  
3 3  
0 1  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/기능 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [greater(STL/CLR)](../dotnet/greater-stl-clr.md)