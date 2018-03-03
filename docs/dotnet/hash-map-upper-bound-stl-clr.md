---
title: 'hash_map:: upper_bound (STL/CLR) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::hash_map::upper_bound
dev_langs:
- C++
helpviewer_keywords:
- upper_bound member [STL/CLR]
ms.assetid: f83e88b4-e15e-49d5-90e4-cf7360c27c30
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 17690c6f99ae8f256003bf54f3bd736f52670e84
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="hashmapupperbound-stlclr"></a>hash_map::upper_bound(STL/CLR)
지정된 된 키와 일치 하는 범위의 끝을 찾습니다.  
  
## <a name="syntax"></a>구문  
  
```  
iterator upper_bound(key_type key);  
```  
  
#### <a name="parameters"></a>매개 변수  
 key  
 검색할 키 값입니다.  
  
## <a name="remarks"></a>설명  
 멤버 함수는 마지막 요소를 결정 `X` 동일한 버킷으로 해시 제어 된 시퀀스의 `key` 과 순서가 및 `key`합니다. 이러한 요소가 존재 하거나 `X` 는 제어 된 시퀀스의 마지막 요소 반환 [hash_map:: end (STL/CLR)](../dotnet/hash-map-end-stl-clr.md)`()`; 그렇지 않으면 의첫번째요소를지정하는반복기를반환`X`. 지정된 된 키와 일치 하는 제어 된 시퀀스의 현재 요소 시퀀스의 끝으로 이동 하려면 사용 합니다.  
  
## <a name="example"></a>예  
  
```  
// cliext_hash_map_upper_bound.cpp   
// compile with: /clr   
#include <cliext/hash_map>   
  
typedef cliext::hash_map<wchar_t, int> Myhash_map;   
int main()   
    {   
    Myhash_map c1;   
    c1.insert(Myhash_map::make_value(L'a', 1));   
    c1.insert(Myhash_map::make_value(L'b', 2));   
    c1.insert(Myhash_map::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Myhash_map::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("upper_bound(L'x')==end() = {0}",   
        c1.upper_bound(L'x') == c1.end());   
  
    Myhash_map::iterator it = c1.upper_bound(L'a');   
    System::Console::WriteLine("*upper_bound(L'a') = [{0} {1}]",   
        it->first, it->second);   
    it = c1.upper_bound(L'b');   
    System::Console::WriteLine("*upper_bound(L'b') = [{0} {1}]",   
        it->first, it->second);   
    return (0);   
    }  
  
```  
  
```Output  
 [a 1] [b 2] [c 3]  
upper_bound(L'x')==end() = True  
*upper_bound(L'a') = [b 2]  
*upper_bound(L'b') = [c 3]  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/hash_map >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [hash_map (STL/CLR)](../dotnet/hash-map-stl-clr.md)   
 [hash_map:: count (STL/CLR)](../dotnet/hash-map-count-stl-clr.md)   
 [hash_map:: equal_range (STL/CLR)](../dotnet/hash-map-equal-range-stl-clr.md)   
 [hash_map:: find (STL/CLR)](../dotnet/hash-map-find-stl-clr.md)   
 [hash_map::lower_bound(STL/CLR)](../dotnet/hash-map-lower-bound-stl-clr.md)