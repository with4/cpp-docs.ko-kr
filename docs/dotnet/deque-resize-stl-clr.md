---
title: 'deque:: resize (STL/CLR) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::deque::resize
dev_langs:
- C++
helpviewer_keywords:
- resize member [STL/CLR]
ms.assetid: c83f3c57-38b3-4706-a124-59bafbf88484
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 0d7e68fa1a58e70d4b414f81ca826e632c8706bd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="dequeresize-stlclr"></a>deque::resize(STL/CLR)
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
 두 멤버 함수를 확인 하는 [deque:: size (STL/CLR)](../dotnet/deque-size-stl-clr.md) `()` 예측이 반환 `new_size`합니다. 제어되는 시퀀스 길이를 늘려야 할 경우 첫 번째 멤버 함수는 값이 `value_type()`인 요소를 추가하지만, 두 번째 멤버 함수는 값이 `val`인 요소를 추가합니다. 더 짧은 제어 되는 시퀀스를 두 멤버 함수는 효과적으로 지울 마지막 요소 [deque:: size (STL/CLR)](../dotnet/deque-size-stl-clr.md) `() -` `new_size` 시간입니다. 제어 되는 시퀀스의 크기가을 사용 하면 `new_size`, 트리밍 하거나 현재 제어 되는 시퀀스를 패딩 하 여 합니다.  
  
## <a name="example"></a>예제  
  
```  
// cliext_deque_resize.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
// construct an empty container and pad with default values   
    cliext::deque<wchar_t> c1;   
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
 **헤더:** \<cliext/q u e >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [deque (STL/CLR)](../dotnet/deque-stl-clr.md)   
 [deque:: clear (STL/CLR)](../dotnet/deque-clear-stl-clr.md)   
 [deque:: erase (STL/CLR)](../dotnet/deque-erase-stl-clr.md)   
 [deque::insert(STL/CLR)](../dotnet/deque-insert-stl-clr.md)