---
title: 'queue:: difference_type (STL/CLR) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::queue::difference_type
dev_langs:
- C++
helpviewer_keywords:
- difference_type member [STL/CLR]
ms.assetid: d7a716e1-b331-4928-bda3-f3c74a57307e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 961a5d259ce0421d2ab66acc56c9116ce0b9bcea
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="queuedifferencetype-stlclr"></a>queue::difference_type(STL/CLR)
두 요소 사이의 부호가 있는 거리의 형식입니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef int difference_type;  
```  
  
## <a name="remarks"></a>설명  
 형식은 음수 수 있는 요소 수를 설명 합니다.  
  
## <a name="example"></a>예제  
  
```  
// cliext_queue_difference_type.cpp   
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
  
// compute negative difference   
    Myqueue::difference_type diff = c1.size();   
    c1.push(L'd');   
    c1.push(L'e');   
    diff -= c1.size();   
    System::Console::WriteLine("pushing 2 = {0}", diff);   
  
// compute positive difference   
    diff = c1.size();   
    c1.pop();   
    c1.pop();   
    c1.pop();   
    diff -= c1.size();   
    System::Console::WriteLine("popping 3 = {0}", diff);   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
pushing 2 = -2  
popping 3 = 3  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/queue >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [queue (STL/CLR)](../dotnet/queue-stl-clr.md)   
 [queue::size_type(STL/CLR)](../dotnet/queue-size-type-stl-clr.md)