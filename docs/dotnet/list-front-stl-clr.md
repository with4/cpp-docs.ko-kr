---
title: 'list:: front (STL/CLR) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::list::front
dev_langs:
- C++
helpviewer_keywords:
- front member [STL/CLR]
ms.assetid: ead6aaaa-b518-4a9c-af80-7189bf872cad
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: a0ec34ee2bff0a494b09b70b19a08c25e041121d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="listfront-stlclr"></a>list::front(STL/CLR)
첫 번째 요소에 액세스합니다.  
  
## <a name="syntax"></a>구문  
  
```  
reference front();  
```  
  
## <a name="remarks"></a>설명  
 멤버 함수는 비어 있어야 하는 제어 된 시퀀스의 첫 번째 요소에 대 한 참조를 반환 합니다. 읽기 또는 존재 하는 것을 알고 있는 경우 첫 번째 요소를 쓰기를 사용 합니다.  
  
## <a name="example"></a>예  
  
```  
// cliext_list_front.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect first item   
    System::Console::WriteLine("front() = {0}", c1.front());   
  
// alter first item and reinspect   
    c1.front() = L'x';   
    for each (wchar_t elem in c1)   
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
 **헤더:** \<cliext/목록 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [list (STL/CLR)](../dotnet/list-stl-clr.md)   
 [list:: back (STL/CLR)](../dotnet/list-back-stl-clr.md)   
 [list:: back_item (STL/CLR)](../dotnet/list-back-item-stl-clr.md)   
 [list::front_item(STL/CLR)](../dotnet/list-front-item-stl-clr.md)