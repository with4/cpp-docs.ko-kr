---
title: 연산자&lt;= (pair) (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::pair::operator<=
dev_langs:
- C++
helpviewer_keywords:
- operator<= member [STL/CLR]
ms.assetid: 94a4cc0a-cef4-4050-bd59-f826bd318e7b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: f3e74b6f11cf54d694ac726670d92cb4e02aa563
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33133664"
---
# <a name="operatorlt-pair-stlclr"></a>연산자&lt;= (pair) (STL/CLR)
보다 작거나 같은 쌍으로 연결 비교 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
template<typename Value1,  
    typename Value2>  
    bool operator<=(pair<Value1, Value2>% left,  
        pair<Value1, Value2>% right);  
```  
  
#### <a name="parameters"></a>매개 변수  
 왼쪽  
 비교할 왼쪽된 쌍입니다.  
  
 오른쪽  
 비교할 오른쪽 쌍입니다.  
  
## <a name="remarks"></a>설명  
 연산자 함수 반환 `!(right < left)`합니다. 테스트를 사용 하는지 여부를 `left` 후 정렬 되지 않은 `right` 때 두 쌍은 요소 별로 비교 합니다.  
  
## <a name="example"></a>예제  
  
```  
// cliext_pair_operator_le.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
    cliext::pair<wchar_t, int> c1(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
    cliext::pair<wchar_t, int> c2(L'x', 4);   
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);   
  
    System::Console::WriteLine("[x 3] <= [x 3] is {0}",   
        c1 <= c1);   
    System::Console::WriteLine("[x 4] <= [x 3] is {0}",   
        c2 <= c1);   
    return (0);   
    }  
  
```  
  
```Output  
[x, 3]  
[x, 4]  
[x 3] <= [x 3] is True  
[x 4] <= [x 3] is False  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/유틸리티 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [pair (STL/CLR)](../dotnet/pair-stl-clr.md)   
 [연산자 = = (pair) (STL/CLR)](../dotnet/operator-equality-pair-stl-clr.md)   
 [operator! = (pair) (STL/CLR)](../dotnet/operator-inequality-pair-stl-clr.md)   
 [연산자\< (pair) (STL/CLR)](../dotnet/operator-less-than-pair-stl-clr.md)   
 [연산자 > = (pair) (STL/CLR)](../dotnet/operator-greater-or-equal-pair-stl-clr.md)   
 [operator> (pair)(STL/CLR)](../dotnet/operator-greater-than-pair-stl-clr.md)