---
title: 'list:: back_item (STL/CLR) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::list::back_item
dev_langs:
- C++
helpviewer_keywords:
- back_item member [STL/CLR]
ms.assetid: 63dcdd21-61f7-4e0f-88a7-c9c8f8a2c50a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: dd753c87dc0ad8409ff084f479306e561bfc75e6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="listbackitem-stlclr"></a>list::back_item(STL/CLR)
마지막 요소에 액세스합니다.  
  
## <a name="syntax"></a>구문  
  
```  
property value_type back_item;  
```  
  
## <a name="remarks"></a>설명  
 비어 있는 제어 된 시퀀스의 마지막 요소를 액세스 하는 속성입니다. 읽기 또는 존재 하는 것을 알고 있는 경우 마지막 요소를 쓰기 사용 합니다.  
  
## <a name="example"></a>예제  
  
```  
// cliext_list_back_item.cpp   
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
  
// inspect last item   
    System::Console::WriteLine("back_item = {0}", c1.back_item);   
  
// alter last item and reinspect   
    c1.back_item = L'x';   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
back_item = c  
 a b x  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/목록 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [list (STL/CLR)](../dotnet/list-stl-clr.md)   
 [list:: back (STL/CLR)](../dotnet/list-back-stl-clr.md)   
 [list:: front (STL/CLR)](../dotnet/list-front-stl-clr.md)   
 [list::front_item(STL/CLR)](../dotnet/list-front-item-stl-clr.md)