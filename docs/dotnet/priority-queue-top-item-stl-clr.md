---
title: 'priority_queue:: top_item (STL/CLR) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::priority_queue::top_item
dev_langs:
- C++
helpviewer_keywords:
- top_item member [STL/CLR]
ms.assetid: d497403b-6b1d-4c6e-a0f4-c744cc5fad75
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 9cc5dc2656a1083b4aaa2b6cadc731a6010968e7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="priorityqueuetopitem-stlclr"></a>priority_queue::top_item(STL/CLR)
우선 순위가 가장 높은 요소에 액세스 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
property value_type back_item;  
```  
  
## <a name="remarks"></a>설명  
 비어 있는 제어 된 시퀀스의 최상위 (가장 높은 우선 순위) 요소를 액세스 하는 속성입니다. 읽기 또는 존재 하는 것을 알고 있는 경우 우선 순위가 가장 높은 요소를 쓰기 사용 합니다.  
  
## <a name="example"></a>예  
  
```  
// cliext_priority_queue_top_item.cpp   
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
    System::Console::WriteLine("top_item = {0}", c1.top_item);   
  
// alter last item and reinspect   
    c1.top_item = L'x';   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
 c a b  
top_item = c  
 x a b  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/queue >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [priority_queue (STL/CLR)](../dotnet/priority-queue-stl-clr.md)   
 [priority_queue::top(STL/CLR)](../dotnet/priority-queue-top-stl-clr.md)