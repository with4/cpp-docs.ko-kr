---
title: 'hash_multimap:: equal_range (STL/CLR) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::hash_multimap::equal_range
dev_langs:
- C++
helpviewer_keywords:
- equal_range member [STL/CLR]
ms.assetid: 3ea11e31-d4af-4d2e-a80b-eafe12c97d0c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: d6ba29c310fed400fd5a02cdb0b055c9e2ea2747
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33111587"
---
# <a name="hashmultimapequalrange-stlclr"></a>hash_multimap::equal_range(STL/CLR)
지정된 키와 일치하는 범위를 찾습니다.  
  
## <a name="syntax"></a>구문  
  
```  
cliext::pair<iterator, iterator> equal_range(key_type key);  
```  
  
#### <a name="parameters"></a>매개 변수  
 key  
 검색할 키 값입니다.  
  
## <a name="remarks"></a>설명  
 멤버 함수는 한 쌍의 반복기를 반환 `cliext::pair<iterator, iterator>(` [hash_multimap:: lower_bound (STL/CLR)](../dotnet/hash-multimap-lower-bound-stl-clr.md) `(key),` [hash_multimap:: upper_bound (STL/CLR)](../dotnet/hash-multimap-upper-bound-stl-clr.md)`(key))`합니다. 지정된 된 키와 일치 하는 제어 된 시퀀스의 현재 요소의 범위를 확인 하려면 사용 합니다.  
  
## <a name="example"></a>예제  
  
```  
// cliext_hash_multimap_equal_range.cpp   
// compile with: /clr   
#include <cliext/hash_map>   
  
typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;   
typedef Myhash_multimap::pair_iter_iter Pairii;   
int main()   
    {   
    Myhash_multimap c1;   
    c1.insert(Myhash_multimap::make_value(L'a', 1));   
    c1.insert(Myhash_multimap::make_value(L'b', 2));   
    c1.insert(Myhash_multimap::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Myhash_multimap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// display results of failed search   
    Pairii pair1 = c1.equal_range(L'x');   
    System::Console::WriteLine("equal_range(L'x') empty = {0}",   
        pair1.first == pair1.second);   
  
// display results of successful search   
    pair1 = c1.equal_range(L'b');   
    for (; pair1.first != pair1.second; ++pair1.first)   
        System::Console::Write(" [{0} {1}]",   
            pair1.first->first, pair1.first->second);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
 [a 1] [b 2] [c 3]  
equal_range(L'x') empty = True  
 [b 2]  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/hash_map >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [hash_multimap (STL/CLR)](../dotnet/hash-multimap-stl-clr.md)   
 [hash_multimap:: count (STL/CLR)](../dotnet/hash-multimap-count-stl-clr.md)   
 [hash_multimap:: find (STL/CLR)](../dotnet/hash-multimap-find-stl-clr.md)   
 [hash_multimap:: lower_bound (STL/CLR)](../dotnet/hash-multimap-lower-bound-stl-clr.md)   
 [hash_multimap::upper_bound(STL/CLR)](../dotnet/hash-multimap-upper-bound-stl-clr.md)