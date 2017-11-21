---
title: 'list:: resize (STL/CLR) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::list::resize
dev_langs: C++
helpviewer_keywords: resize member [STL/CLR]
ms.assetid: c4b8d41f-a62b-4dbc-8568-0e0a9da24016
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 1bded7710d15aba5a87f763d530cc2054d8fdbc4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="listresize-stlclr"></a>list::resize(STL/CLR)
요소의 수를 변경합니다.  
  
## <a name="syntax"></a>구문  
  
```  
void resize(size_type new_size);  
void resize(size_type new_size, value_type val);  
```  
  
#### <a name="parameters"></a>매개 변수  
 new_size  
 제어 된 시퀀스의 새 크기입니다.  
  
 val  
 안쪽 여백 요소의 값입니다.  
  
## <a name="remarks"></a>설명  
 두 멤버 함수를 확인 하는 [list:: size (STL/CLR)](../dotnet/list-size-stl-clr.md) `()` 예측이 반환 `new_size`합니다. 제어되는 시퀀스 길이를 늘려야 할 경우 첫 번째 멤버 함수는 값이 `value_type()`인 요소를 추가하지만, 두 번째 멤버 함수는 값이 `val`인 요소를 추가합니다. 더 짧은 제어 되는 시퀀스를 두 멤버 함수는 효과적으로 지울 마지막 요소 [list:: size (STL/CLR)](../dotnet/list-size-stl-clr.md) `() -` `new_size` 시간입니다. 제어 되는 시퀀스의 크기가을 사용 하면 `new_size`, 트리밍 하거나 현재 제어 되는 시퀀스를 패딩 하 여 합니다.  
  
## <a name="example"></a>예제  
  
```  
// cliext_list_resize.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
// construct an empty container and pad with default values   
    cliext::list<wchar_t> c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
    c1.resize(4);   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", (int)elem);   
    System::Console::WriteLine();   
  
// resize to empty   
    c1.resize(0);   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// resize and pad   
    c1.resize(5, L'x');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
size() = 0  
 0 0 0 0  
size() = 0  
 x x x x x  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/목록 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [list (STL/CLR)](../dotnet/list-stl-clr.md)   
 [list:: clear (STL/CLR)](../dotnet/list-clear-stl-clr.md)   
 [list:: erase (STL/CLR)](../dotnet/list-erase-stl-clr.md)   
 [list::insert(STL/CLR)](../dotnet/list-insert-stl-clr.md)