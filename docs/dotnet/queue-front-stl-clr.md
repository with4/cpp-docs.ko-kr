---
title: 'queue:: front (STL/CLR) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::queue::front
dev_langs: C++
helpviewer_keywords: front member [STL/CLR]
ms.assetid: 9d7bb95f-5896-42f7-86fa-004a7a65cc94
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d3f214fdef7ab79876d5f4d6718db8292dd95eee
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="queuefront-stlclr"></a>queue::front(STL/CLR)
첫 번째 요소에 액세스합니다.  
  
## <a name="syntax"></a>구문  
  
```  
reference front();  
```  
  
## <a name="remarks"></a>설명  
 멤버 함수는 비어 있어야 하는 제어 된 시퀀스의 첫 번째 요소에 대 한 참조를 반환 합니다. 존재 하는 것을 알고 있는 경우 첫 번째 요소를 액세스할 수 사용 합니다.  
  
## <a name="example"></a>예제  
  
```  
// cliext_queue_front.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::queue<wchar_t> Myqueue;   
int main()   
    {   
    Myqueue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect first item   
    System::Console::WriteLine("front() = {0}", c1.front());   
  
// alter first item and reinspect   
    c1.front() = L'x';   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
front() = a  
 x b c  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/queue >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [queue (STL/CLR)](../dotnet/queue-stl-clr.md)   
 [queue:: back (STL/CLR)](../dotnet/queue-back-stl-clr.md)   
 [queue:: back_item (STL/CLR)](../dotnet/queue-back-item-stl-clr.md)   
 [queue::front_item(STL/CLR)](../dotnet/queue-front-item-stl-clr.md)