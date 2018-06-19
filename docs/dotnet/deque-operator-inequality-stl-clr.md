---
title: 'deque:: operator! = (STL/CLR) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::deque::operator!=
dev_langs:
- C++
helpviewer_keywords:
- operator!= member [STL/CLR]
ms.assetid: c23c7bd1-813e-4518-9947-eb13d1176a13
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 46898ab8c6f747dbd72c94e490ec79034231bf81
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33109923"
---
# <a name="dequeoperator-stlclr"></a>deque::operator!=(STL/CLR)
Deque에 같지 비교 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
template<typename Value>  
    bool operator!=(deque<Value>% left,  
        deque<Value>% right);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `left`  
 비교할 왼쪽 컨테이너입니다.  
  
 `right`  
 비교할 오른쪽 컨테이너입니다.  
  
## <a name="remarks"></a>설명  
 연산자 함수 반환 `!(left == right)`합니다. 테스트를 사용 하는지 여부를 `left` 동일 정렬 되지 않은 `right` 두 deque 경우 요소 별로 비교 합니다.  
  
## <a name="example"></a>예제  
  
```cpp  
// cliext_deque_operator_ne.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    cliext::deque<wchar_t> c2;   
    c2.push_back(L'a');   
    c2.push_back(L'b');   
    c2.push_back(L'd');   
  
// display contents " a b d"   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("[a b c] != [a b c] is {0}",   
        c1 != c1);   
    System::Console::WriteLine("[a b c] != [a b d] is {0}",   
        c1 != c2);   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
 a b d  
[a b c] != [a b c] is False  
[a b c] != [a b d] is True  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/q u e >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [deque (STL/CLR)](../dotnet/deque-stl-clr.md)   
 [연산자 = = (deque) (STL/CLR)](../dotnet/operator-equality-deque-stl-clr.md)   
 [연산자\< (deque) (STL/CLR)](../dotnet/operator-less-than-deque-stl-clr.md)   
 [연산자 > = (deque) (STL/CLR)](../dotnet/operator-greater-or-equal-deque-stl-clr.md)   
 [연산자 > (deque) (STL/CLR)](../dotnet/operator-greater-than-deque-stl-clr.md)   
 [operator<= (deque)(STL/CLR)](../dotnet/operator-less-or-equal-deque-stl-clr.md)