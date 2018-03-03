---
title: 'priority_queue:: top (STL/CLR) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::priority_queue::top
dev_langs:
- C++
helpviewer_keywords:
- top member [STL/CLR]
ms.assetid: e45211d5-e6df-4c03-97fd-57afb87af58c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: c1614d1babb06aa3b36b6932fd23c1f2700a3ee3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="priorityqueuetop-stlclr"></a>priority_queue::top(STL/CLR)
우선 순위가 가장 높은 요소에 액세스 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
reference top();  
```  
  
## <a name="remarks"></a>설명  
 멤버 함수는 비어 있는 제어 된 시퀀스의 최상위 (가장 높은 우선 순위) 요소에 대 한 참조를 반환 합니다. 존재 하는 것을 알고 있는 경우 우선 순위가 가장 높은 요소를 액세스할 수 사용 합니다.  
  
## <a name="example"></a>예  
  
```  
// cliext_priority_queue_top.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::priority_queue<wchar_t> Mypriority_queue;   
int main()   
    {   
    Mypriority_queue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect last item   
    System::Console::WriteLine("top() = {0}", c1.top());   
  
// alter last item and reinspect   
    c1.top() = L'x';   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
 c a b  
top() = c  
 x a b  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/queue >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [priority_queue (STL/CLR)](../dotnet/priority-queue-stl-clr.md)   
 [priority_queue::top_item(STL/CLR)](../dotnet/priority-queue-top-item-stl-clr.md)