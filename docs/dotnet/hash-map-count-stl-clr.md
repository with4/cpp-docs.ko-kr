---
title: 'hash_map:: count (STL/CLR) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::hash_map::Count
dev_langs:
- C++
helpviewer_keywords:
- count member [STL/CLR]
ms.assetid: 1d02f764-d24f-4c8c-8a62-63074fe49aa8
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 3b1f5536301ecd7e137bc80dc321321ee4d3d55b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="hashmapcount-stlclr"></a>hash_map::count(STL/CLR)
지정한 키와 일치하는 요소의 수를 찾습니다.  
  
## <a name="syntax"></a>구문  
  
```  
size_type count(key_type key);  
```  
  
#### <a name="parameters"></a>매개 변수  
 key  
 검색할 키 값입니다.  
  
## <a name="remarks"></a>설명  
 멤버 함수는 사용 순서 지정이 동일할 제어 된 시퀀스의 요소 수를 반환 `key`합니다. 지정된 된 키와 일치 하는 제어 되는 시퀀스의 현재 요소 수를 확인 하려면 사용 합니다.  
  
## <a name="example"></a>예  
  
```  
// cliext_hash_map_count.cpp   
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
  
    System::Console::WriteLine("count(L'A') = {0}", c1.count(L'A'));   
    System::Console::WriteLine("count(L'b') = {0}", c1.count(L'b'));   
    System::Console::WriteLine("count(L'C') = {0}", c1.count(L'C'));   
    return (0);   
    }  
  
```  
  
```Output  
 [a 1] [b 2] [c 3]  
count(L'A') = 0  
count(L'b') = 1  
count(L'C') = 0  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/hash_map >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [hash_map (STL/CLR)](../dotnet/hash-map-stl-clr.md)   
 [hash_map::equal_range(STL/CLR)](../dotnet/hash-map-equal-range-stl-clr.md)