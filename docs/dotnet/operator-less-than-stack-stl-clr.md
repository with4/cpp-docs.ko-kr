---
title: 연산자&lt; (stack) (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::stack::operator<
dev_langs:
- C++
helpviewer_keywords:
- operator< member [STL/CLR]
ms.assetid: 77f8dd42-89d1-4ce1-a7ec-04c3a45dd3ee
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 77ed992b33dee758b6ca7d2997135b704863c02c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="operatorlt-stack-stlclr"></a>연산자&lt; (stack) (STL/CLR)
스택 비교 보다 작습니다.  
  
## <a name="syntax"></a>구문  
  
```  
template<typename Value,  
    typename Container>  
    bool operator<(stack<Value, Container>% left,  
        stack<Value, Container>% right);  
```  
  
#### <a name="parameters"></a>매개 변수  
 왼쪽  
 비교할 왼쪽 컨테이너입니다.  
  
 오른쪽  
 비교할 오른쪽 컨테이너입니다.  
  
## <a name="remarks"></a>설명  
 연산자 함수 이면 true를 반환, 가장 낮은 위치에 대 한 `i` 를 `!(right[i] < left[i])` 도 true 하는 것이 `left[i] < right[i]`합니다. 그렇지 않으면 반환 `left->` [stack:: size (STL/CLR)](../dotnet/stack-size-stl-clr.md) `() <` `right->size()` 테스트를 사용 하는지 여부를 `left` 앞에 정렬 `right` 두 스택 요소 별로 비교를 하는 경우.  
  
## <a name="example"></a>예제  
  
```  
// cliext_stack_operator_lt.cpp   
// compile with: /clr   
#include <cliext/stack>   
  
typedef cliext::stack<wchar_t> Mystack;   
int main()   
    {   
    Mystack c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    Mystack c2;   
    c2.push(L'a');   
    c2.push(L'b');   
    c2.push(L'd');   
  
// display contents " a b d"   
    for each (wchar_t elem in c2.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("[a b c] < [a b c] is {0}",   
        c1 < c1);   
    System::Console::WriteLine("[a b c] < [a b d] is {0}",   
        c1 < c2);   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
 a b d  
[a b c] < [a b c] is False  
[a b c] < [a b d] is True  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/스택 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [stack (STL/CLR)](../dotnet/stack-stl-clr.md)   
 [연산자 = = (stack) (STL/CLR)](../dotnet/operator-equality-stack-stl-clr.md)   
 [operator! = (stack) (STL/CLR)](../dotnet/operator-inequality-stack-stl-clr.md)   
 [연산자 > = (stack) (STL/CLR)](../dotnet/operator-greater-or-equal-stack-stl-clr.md)   
 [연산자 > (stack) (STL/CLR)](../dotnet/operator-greater-than-stack-stl-clr.md)   
 [operator<= (stack)(STL/CLR)](../dotnet/operator-less-or-equal-stack-stl-clr.md)