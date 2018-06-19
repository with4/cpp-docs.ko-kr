---
title: 'set:: rbegin (STL/CLR) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::set::rbegin
dev_langs:
- C++
helpviewer_keywords:
- rbegin member [STL/CLR]
ms.assetid: b9da72dc-0b75-489e-b179-74c27a4bcfb7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 7636c2f3722ab6e6da86de36e9876c39c047b894
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33162927"
---
# <a name="setrbegin-stlclr"></a>set::rbegin(STL/CLR)
제어되는 역방향 시퀀스의 시작을 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
reverse_iterator rbegin();  
```  
  
## <a name="remarks"></a>설명  
 멤버 함수는 빈 시퀀스의 시작 부분 바로 다음 또는 제어 된 시퀀스의 마지막 요소를 지정 하는 역방향 반복기를 반환 합니다. 따라서을 지정 된 `beginning` 역방향 시퀀스의 합니다. 지정 하는 반복기를 사용 하면는 `current` 제어 된 시퀀스를 역순으로 표시 하지만 해당 상태의 시작 부분 제어 된 시퀀스의 길이가 변경 되 면 변경할 수 있습니다.  
  
## <a name="example"></a>예제  
  
```  
// cliext_set_rbegin.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::set<wchar_t> Myset;   
int main()   
    {   
    Myset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect first two items in reversed sequence   
    Myset::reverse_iterator rit = c1.rbegin();   
    System::Console::WriteLine("*rbegin() = {0}", *rit);   
    System::Console::WriteLine("*++rbegin() = {0}", *++rit);   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
*rbegin() = c  
*++rbegin() = b  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/set >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [set (STL/CLR)](../dotnet/set-stl-clr.md)   
 [set:: begin (STL/CLR)](../dotnet/set-begin-stl-clr.md)   
 [set:: end (STL/CLR)](../dotnet/set-end-stl-clr.md)   
 [set::rend(STL/CLR)](../dotnet/set-rend-stl-clr.md)