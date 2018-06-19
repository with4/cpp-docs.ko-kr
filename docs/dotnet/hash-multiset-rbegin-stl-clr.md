---
title: 'hash_multiset:: rbegin (STL/CLR) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::hash_multiset::rbegin
dev_langs:
- C++
helpviewer_keywords:
- rbegin member [STL/CLR]
ms.assetid: 69a06d99-3262-495b-9956-5f155162da33
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: a0945e5d27e8c2d0142eaf310baf23a7952900f6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33128607"
---
# <a name="hashmultisetrbegin-stlclr"></a>hash_multiset::rbegin(STL/CLR)
제어되는 역방향 시퀀스의 시작을 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
reverse_iterator rbegin();  
```  
  
## <a name="remarks"></a>설명  
 멤버 함수는 빈 시퀀스의 시작 부분 바로 다음 또는 제어 된 시퀀스의 마지막 요소를 지정 하는 역방향 반복기를 반환 합니다. 따라서을 지정 된 `beginning` 역방향 시퀀스의 합니다. 지정 하는 반복기를 사용 하면는 `current` 제어 된 시퀀스를 역순으로 표시 하지만 해당 상태의 시작 부분 제어 된 시퀀스의 길이가 변경 되 면 변경할 수 있습니다.  
  
## <a name="example"></a>예제  
  
```  
// cliext_hash_multiset_rbegin.cpp   
// compile with: /clr   
#include <cliext/hash_set>   
  
typedef cliext::hash_multiset<wchar_t> Myhash_multiset;   
int main()   
    {   
    Myhash_multiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect first two items in reversed sequence   
    Myhash_multiset::reverse_iterator rit = c1.rbegin();   
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
 **헤더:** \<cliext/hash_set >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [hash_multiset (STL/CLR)](../dotnet/hash-multiset-stl-clr.md)   
 [hash_multiset:: begin (STL/CLR)](../dotnet/hash-multiset-begin-stl-clr.md)   
 [hash_multiset:: end (STL/CLR)](../dotnet/hash-multiset-end-stl-clr.md)   
 [hash_multiset::rend(STL/CLR)](../dotnet/hash-multiset-rend-stl-clr.md)