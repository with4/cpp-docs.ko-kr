---
title: "연산자 = = (pair) (STL/CLR) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::pair::operator==
dev_langs: C++
helpviewer_keywords: operator== member [STL/CLR]
ms.assetid: 2b4879a1-f326-4fb3-b113-bd8d457f9802
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 15be265d13ef202e0a3b21fea61146fc3ae502a8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="operator-pair-stlclr"></a>operator== (pair)(STL/CLR)
쌍 같은지 비교 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
template<typename Value1,  
    typename Value2>  
    bool operator==(pair<Value1, Value2>% left,  
        pair<Value1, Value2>% right);  
```  
  
#### <a name="parameters"></a>매개 변수  
 왼쪽  
 비교할 왼쪽된 쌍입니다.  
  
 오른쪽  
 비교할 오른쪽 쌍입니다.  
  
## <a name="remarks"></a>설명  
 연산자 함수 반환 `left.first ==` `right.first &&` `left.second ==` `right.second`합니다. 테스트를 사용 하는지 여부를 `left` 정렬 되는 동일 `right` 때 두 쌍은 요소 별로 비교 합니다.  
  
## <a name="example"></a>예  
  
```  
// cliext_pair_operator_eq.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
    cliext::pair<wchar_t, int> c1(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
    cliext::pair<wchar_t, int> c2(L'x', 4);   
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);   
  
    System::Console::WriteLine("[x 3] == [x 3] is {0}",   
        c1 == c1);   
    System::Console::WriteLine("[x 3] == [x 4] is {0}",   
        c1 == c2);   
    return (0);   
    }  
  
```  
  
```Output  
[x, 3]  
[x, 4]  
[x 3] == [x 3] is True  
[x 3] == [x 4] is False  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/유틸리티 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [pair (STL/CLR)](../dotnet/pair-stl-clr.md)   
 [operator! = (pair) (STL/CLR)](../dotnet/operator-inequality-pair-stl-clr.md)   
 [연산자\< (pair) (STL/CLR)](../dotnet/operator-less-than-pair-stl-clr.md)   
 [연산자 > = (pair) (STL/CLR)](../dotnet/operator-greater-or-equal-pair-stl-clr.md)   
 [연산자 > (pair) (STL/CLR)](../dotnet/operator-greater-than-pair-stl-clr.md)   
 [operator<= (pair)(STL/CLR)](../dotnet/operator-less-or-equal-pair-stl-clr.md)