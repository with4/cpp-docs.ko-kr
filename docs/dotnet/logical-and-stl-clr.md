---
title: logical_and (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::logical_and
dev_langs:
- C++
helpviewer_keywords:
- logical_and function [STL/CLR]
ms.assetid: ae103802-11e0-4060-a4f3-4f6fdc209e7c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 62707fbcb0fd78c019fea886f4975973abbcc5aa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="logicaland-stlclr"></a>logical_and(STL/CLR)
함수를 설명 하는 템플릿 클래스, 호출 되 면 true를 반환 하는 첫 번째 인수와 두 번째 테스트는 모두 true 일 경우에 합니다. 사용 하면 해당 인수 형식 기준으로 함수 개체를 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
template<typename Arg>  
    ref class logical_and  
    { // wrap operator()  
public:  
    typedef Arg first_argument_type;  
    typedef Arg second_argument_type;  
    typedef bool result_type;  
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<  
        first_argument_type, second_argument_type, result_type>  
        delegate_type;  
  
    logical_and();  
    logical_and(logical_and<Arg>% right);  
  
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
|logical_and|함수를 생성합니다.|  
  
|연산자|설명|  
|--------------|-----------------|  
|operator()|원하는 함수를 계산합니다.|  
|연산자 delegate_type ^|대리자에 함수를 캐스팅합니다.|  
  
## <a name="remarks"></a>설명  
 두 인수 함수를 설명 하는 템플릿 클래스입니다. 멤버 연산자 정의 `operator()` 개체 함수로 호출 될 때 있도록 true를 반환 하는지만 첫 번째 인수 및 두 번째 테스트는 모두 true입니다.  
  
 함수 인수는 형식의 개체를 전달할 수도 있습니다 `delegate_type^` 적절 하 게 변환 됩니다.  
  
## <a name="example"></a>예  
  
```  
// cliext_logical_and.cpp   
// compile with: /clr   
#include <cliext/algorithm>   
#include <cliext/functional>   
#include <cliext/vector>   
  
typedef cliext::vector<int> Myvector;   
int main()   
    {   
    Myvector c1;   
    c1.push_back(2);   
    c1.push_back(0);   
    Myvector c2;   
    c2.push_back(3);   
    c2.push_back(0);   
    Myvector c3(2, 0);   
  
// display initial contents " 1 0" and " 1 0"   
    for each (int elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    for each (int elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display   
    cliext::transform(c1.begin(), c1.begin() + 2,   
        c2.begin(), c3.begin(), cliext::logical_and<int>());   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
2 0  
3 0  
1 0  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/기능 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [logical_or(STL/CLR)](../dotnet/logical-or-stl-clr.md)