---
title: 'list:: end (STL/CLR) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::list::end
dev_langs:
- C++
helpviewer_keywords:
- end member [STL/CLR]
ms.assetid: c3444164-2c6e-4cbd-8765-1ce7d30fc43e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: bcccbb2332988e1b2a203a61688b0ebceb3defb1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="listend-stlclr"></a>list::end(STL/CLR)
제어되는 시퀀스의 끝을 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
iterator end();  
```  
  
## <a name="remarks"></a>설명  
 멤버 함수는 제어 된 시퀀스의 끝 바로 다음을 가리키는 임의 액세스 반복기를 반환합니다. 제어 된 시퀀스의 끝을 지정 하는 반복기를 가져올 사용 해당 상태 대상이 제어 된 시퀀스의 길이가 변경 하는 경우 변경 되지 않습니다.  
  
## <a name="example"></a>예제  
  
```  
// cliext_list_end.cpp   
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
  
// inspect last two items   
    cliext::list<wchar_t>::iterator it = c1.end();   
    --it;   
    System::Console::WriteLine("*-- --end() = {0}", *--it);   
    System::Console::WriteLine("*--end() = {0}", *++it);   
  
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
*-- --end() = b  
*--end() = c  
 a x y  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/목록 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [list (STL/CLR)](../dotnet/list-stl-clr.md)   
 [list:: back (STL/CLR)](../dotnet/list-back-stl-clr.md)   
 [list:: back_item (STL/CLR)](../dotnet/list-back-item-stl-clr.md)   
 [list::begin(STL/CLR)](../dotnet/list-begin-stl-clr.md)