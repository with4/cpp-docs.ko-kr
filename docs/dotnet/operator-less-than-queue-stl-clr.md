---
title: "연산자&lt; (queue) (STL/CLR) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::queue::operator<
dev_langs: C++
helpviewer_keywords: operator< member [STL/CLR]
ms.assetid: 2c981e2b-9a88-4b4a-8060-9ac24d5631f5
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: a4cebd9330dd58d93a0afa4b87ed09ddeab51373
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="operatorlt-queue-stlclr"></a>연산자&lt; (queue) (STL/CLR)
큐 비교 보다 작습니다.  
  
## <a name="syntax"></a>구문  
  
```  
template<typename Value,  
    typename Container>  
    bool operator<(queue<Value, Container>% left,  
        queue<Value, Container>% right);  
```  
  
#### <a name="parameters"></a>매개 변수  
 왼쪽  
 비교할 왼쪽 컨테이너입니다.  
  
 오른쪽  
 비교할 오른쪽 컨테이너입니다.  
  
## <a name="remarks"></a>설명  
 연산자 함수 이면 true를 반환, 가장 낮은 위치에 대 한 `i` 를 `!(right[i] < left[i])` 도 true 하는 것이 `left[i] < right[i]`합니다. 그렇지 않으면 반환 `left->` [queue:: size (STL/CLR)](../dotnet/queue-size-stl-clr.md) `() <` `right->size()` 테스트를 사용 하는지 여부를 `left` 앞에 정렬 `right` 때 두 개의 큐는 요소 별로 비교 합니다.  
  
## <a name="example"></a>예  
  
```  
// cliext_queue_operator_lt.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::queue<wchar_t> Myqueue;   
int main()   
    {   
    Myqueue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    Myqueue c2;   
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
 **헤더:** \<cliext/queue >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [queue (STL/CLR)](../dotnet/queue-stl-clr.md)   
 [연산자 = = (queue) (STL/CLR)](../dotnet/operator-equality-queue-stl-clr.md)   
 [operator! = (queue) (STL/CLR)](../dotnet/operator-inequality-queue-stl-clr.md)   
 [연산자 > = (queue) (STL/CLR)](../dotnet/operator-greater-or-equal-queue-stl-clr.md)   
 [연산자 > (queue) (STL/CLR)](../dotnet/operator-greater-than-queue-stl-clr.md)   
 [operator<= (queue)(STL/CLR)](../dotnet/operator-less-or-equal-queue-stl-clr.md)