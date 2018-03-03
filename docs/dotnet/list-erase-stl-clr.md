---
title: 'list:: erase (STL/CLR) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::list::erase
dev_langs:
- C++
helpviewer_keywords:
- erase member [STL/CLR]
ms.assetid: 78705058-1e83-441d-b267-d4fb56451c0b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 54595b61ddd21ccd81cf4f2846224789861cb480
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="listerase-stlclr"></a>list::erase(STL/CLR)
지정된 위치에 있는 요소를 제거합니다.  
  
## <a name="syntax"></a>구문  
  
```  
iterator erase(iterator where);  
iterator erase(iterator first, iterator last);  
```  
  
#### <a name="parameters"></a>매개 변수  
 첫 번째  
 범위를 지우려면의 시작입니다.  
  
 last  
 범위를 지우려면의 끝입니다.  
  
 형식에 대한 설명  
 지울 요소입니다.  
  
## <a name="remarks"></a>설명  
 첫 번째 멤버 함수는 `where`로 지정된 제어 시퀀스의 요소를 제거합니다. 단일 요소를 제거 하려면 사용 합니다.  
  
 두 번째 멤버 함수는 [`first`, `last`]의 범위에서 제어되는 시퀀스의 요소를 제거합니다. 0 개 이상의 연속 요소를 제거 하려면 사용 합니다.  
  
 제거 된 요소 뒤에 남은 첫 번째 요소를 지정 하는 반복기를 반환 하는 두 멤버 함수 또는 [list:: end (STL/CLR)](../dotnet/list-end-stl-clr.md) `()` 이러한 요소가 없을 경우.  
  
 요소를 지운 경우에 요소 복사본의 수는 시퀀스의 할수록 끝과 여 지우기의 끝 간 요소 수에 비례 합니다. (시퀀스의 끝에 하나 이상의 요소를 지우는 중 요소 복사본이 발생 합니다.)  
  
## <a name="example"></a>예  
  
```  
// cliext_list_erase.cpp   
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
  
// erase an element and reinspect   
    System::Console::WriteLine("erase(begin()) = {0}",   
        *c1.erase(c1.begin()));   
  
// add elements and display " b c d e"   
    c1.push_back(L'd');   
    c1.push_back(L'e');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// erase all but end   
    cliext::list<wchar_t>::iterator it = c1.end();   
    System::Console::WriteLine("erase(begin(), end()-1) = {0}",   
        *c1.erase(c1.begin(), --it));   
    System::Console::WriteLine("size() = {0}", c1.size());   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
erase(begin()) = b  
 b c d e  
erase(begin(), end()-1) = e  
size() = 1  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/목록 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [list (STL/CLR)](../dotnet/list-stl-clr.md)   
 [list::clear(STL/CLR)](../dotnet/list-clear-stl-clr.md)