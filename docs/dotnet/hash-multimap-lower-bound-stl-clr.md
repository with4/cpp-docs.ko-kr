---
title: 'hash_multimap:: lower_bound (STL/CLR) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::hash_multimap::lower_bound
dev_langs: C++
helpviewer_keywords: lower_bound member [STL/CLR]
ms.assetid: c61091ef-8364-4447-bdd2-a402cbc05f05
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 87d55d0af7be1a6fd9653dfdf54c2f7ba7efefea
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="hashmultimaplowerbound-stlclr"></a>hash_multimap::lower_bound(STL/CLR)
지정된 된 키와 일치 하는 범위의 시작 부분을 찾습니다.  
  
## <a name="syntax"></a>구문  
  
```  
iterator lower_bound(key_type key);  
```  
  
#### <a name="parameters"></a>매개 변수  
 key  
 검색할 키 값입니다.  
  
## <a name="remarks"></a>설명  
 멤버 함수는 첫 번째 요소를 결정 `X` 동일한 버킷으로 해시 제어 된 시퀀스의 `key` 과 순서가 및 `key`합니다. 이러한 요소가 있는 경우 반환 [hash_multimap:: end (STL/CLR)](../dotnet/hash-multimap-end-stl-clr.md)`()`; 그렇지 않으면 지정 하는 반복기를 반환 `X`합니다. 지정된 된 키와 일치 하는 제어 된 시퀀스의 요소 시퀀스의 시작 부분을 현재 찾을 사용 합니다.  
  
## <a name="example"></a>예제  
  
```  
// cliext_hash_multimap_lower_bound.cpp   
// compile with: /clr   
#include <cliext/hash_map>   
  
typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;   
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
  
    System::Console::WriteLine("lower_bound(L'x')==end() = {0}",   
        c1.lower_bound(L'x') == c1.end());   
  
    Myhash_multimap::iterator it = c1.lower_bound(L'a');   
    System::Console::WriteLine("*lower_bound(L'a') = [{0} {1}]",   
        it->first, it->second);   
    it = c1.lower_bound(L'b');   
    System::Console::WriteLine("*lower_bound(L'b') = [{0} {1}]",   
        it->first, it->second);   
    return (0);   
    }  
  
```  
  
```Output  
 [a 1] [b 2] [c 3]  
lower_bound(L'x')==end() = True  
*lower_bound(L'a') = [a 1]  
*lower_bound(L'b') = [b 2]  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/hash_map >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [hash_multimap (STL/CLR)](../dotnet/hash-multimap-stl-clr.md)   
 [hash_multimap:: count (STL/CLR)](../dotnet/hash-multimap-count-stl-clr.md)   
 [hash_multimap:: equal_range (STL/CLR)](../dotnet/hash-multimap-equal-range-stl-clr.md)   
 [hash_multimap:: find (STL/CLR)](../dotnet/hash-multimap-find-stl-clr.md)   
 [hash_multimap::upper_bound(STL/CLR)](../dotnet/hash-multimap-upper-bound-stl-clr.md)