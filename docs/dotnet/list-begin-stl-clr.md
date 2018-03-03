---
title: 'list:: begin (STL/CLR) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::list::begin
dev_langs:
- C++
helpviewer_keywords:
- begin member [STL/CLR]
ms.assetid: 3431467b-951a-498a-af8d-50f631da1646
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: a98c73ae1bd89b4c963b3f65df86c0df5ac4574b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="listbegin-stlclr"></a>list::begin(STL/CLR)
제어되는 시퀀스의 시작을 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
iterator begin();  
```  
  
## <a name="remarks"></a>설명  
 멤버 함수는 제어 되는 시퀀스 또는 빈 시퀀스의 끝 바로 다음 첫 번째 요소를 지정 하는 임의 액세스 반복기를 반환 합니다. 지정 하는 반복기를 사용 하면는 `current` 제어 된 시퀀스의 길이가 변경 하는 경우의 상태 제어 된 시퀀스의 시작 부분을 변경할 수 있습니다.  
  
## <a name="example"></a>예  
  
```  
// cliext_list_begin.cpp   
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
  
// inspect first two items   
    cliext::list<wchar_t>::iterator it = c1.begin();   
    System::Console::WriteLine("*begin() = {0}", *it);   
    System::Console::WriteLine("*++begin() = {0}", *++it);   
  
// alter first two items and reinspect   
    *--it = L'x';   
    *++it = L'y';   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
*begin() = a  
*++begin() = b  
 x y c  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/목록 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [list (STL/CLR)](../dotnet/list-stl-clr.md)   
 [list:: end (STL/CLR)](../dotnet/list-end-stl-clr.md)   
 [list:: front (STL/CLR)](../dotnet/list-front-stl-clr.md)   
 [list::front_item(STL/CLR)](../dotnet/list-front-item-stl-clr.md)