---
title: 'deque:: erase (STL/CLR) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::deque::erase
dev_langs:
- C++
helpviewer_keywords:
- erase member [STL/CLR]
ms.assetid: 831fbc2b-604f-446b-88bc-b37531304c33
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 5afcc69c27cf96f31d85b4c48d57540669941cbc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="dequeerase-stlclr"></a>deque::erase(STL/CLR)
지정된 위치에 있는 요소를 제거합니다.  
  
## <a name="syntax"></a>구문  
  
```  
iterator erase(iterator where);  
iterator erase(iterator first, iterator last);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `first`  
 범위를 지우려면의 시작입니다.  
  
 `last`  
 범위를 지우려면의 끝입니다.  
  
 `where`  
 지울 요소입니다.  
  
## <a name="remarks"></a>설명  
 첫 번째 멤버 함수는 `where`로 지정된 제어 시퀀스의 요소를 제거합니다. 단일 요소를 제거 하려면 사용 합니다.  
  
 두 번째 멤버 함수는 [`first`, `last`]의 범위에서 제어되는 시퀀스의 요소를 제거합니다. 0 개 이상의 연속 요소를 제거 하려면 사용 합니다.  
  
 제거 된 요소 뒤에 남은 첫 번째 요소를 지정 하는 반복기를 반환 하는 두 멤버 함수 또는 [deque:: end (STL/CLR)](../dotnet/deque-end-stl-clr.md) `()` 이러한 요소가 없을 경우.  
  
 요소를 지운 경우에 요소 복사본의 수는 시퀀스의 할수록 끝과 여 지우기의 끝 간 요소 수에 비례 합니다. (시퀀스의 끝에 하나 이상의 요소를 지우는 중 요소 복사본이 발생 합니다.)  
  
## <a name="example"></a>예제  
  
```cpp  
// cliext_deque_erase.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
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
    cliext::deque<wchar_t>::iterator it = c1.end();   
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
 **헤더:** \<cliext/q u e >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [deque (STL/CLR)](../dotnet/deque-stl-clr.md)   
 [deque::clear(STL/CLR)](../dotnet/deque-clear-stl-clr.md)