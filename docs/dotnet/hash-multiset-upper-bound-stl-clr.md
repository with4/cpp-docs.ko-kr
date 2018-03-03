---
title: 'hash_multiset:: upper_bound (STL/CLR) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::hash_multiset::upper_bound
dev_langs:
- C++
helpviewer_keywords:
- upper_bound member [STL/CLR]
ms.assetid: d5be0d79-ae60-42bb-8a53-051bc374407d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: ad4ff8c26b740b3de246a7f111f60fc3c9e20771
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="hashmultisetupperbound-stlclr"></a>hash_multiset::upper_bound(STL/CLR)
지정된 된 키와 일치 하는 범위의 끝을 찾습니다.  
  
## <a name="syntax"></a>구문  
  
```  
iterator upper_bound(key_type key);  
```  
  
#### <a name="parameters"></a>매개 변수  
 key  
 검색할 키 값입니다.  
  
## <a name="remarks"></a>설명  
 멤버 함수는 마지막 요소를 결정 `X` 동일한 버킷으로 해시 제어 된 시퀀스의 `key` 과 순서가 및 `key`합니다. 이러한 요소가 존재 하거나 `X` 는 제어 된 시퀀스의 마지막 요소 반환 [hash_multiset:: end (STL/CLR)](../dotnet/hash-multiset-end-stl-clr.md)`()`; 그렇지 않으면의 첫 번째 요소를 지정 하는 반복기를 반환 `X`. 지정된 된 키와 일치 하는 제어 된 시퀀스의 현재 요소 시퀀스의 끝으로 이동 하려면 사용 합니다.  
  
## <a name="example"></a>예  
  
```  
// cliext_hash_multiset_upper_bound.cpp   
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
  
    System::Console::WriteLine("upper_bound(L'x')==end() = {0}",   
        c1.upper_bound(L'x') == c1.end());   
  
    System::Console::WriteLine("*upper_bound(L'a') = {0}",   
        *c1.upper_bound(L'a'));   
    System::Console::WriteLine("*upper_bound(L'b') = {0}",   
        *c1.upper_bound(L'b'));   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
upper_bound(L'x')==end() = True  
*upper_bound(L'a') = b  
*upper_bound(L'b') = c  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/hash_set >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [hash_multiset (STL/CLR)](../dotnet/hash-multiset-stl-clr.md)   
 [hash_multiset:: count (STL/CLR)](../dotnet/hash-multiset-count-stl-clr.md)   
 [hash_multiset:: equal_range (STL/CLR)](../dotnet/hash-multiset-equal-range-stl-clr.md)   
 [hash_multiset:: find (STL/CLR)](../dotnet/hash-multiset-find-stl-clr.md)   
 [hash_multiset::lower_bound(STL/CLR)](../dotnet/hash-multiset-lower-bound-stl-clr.md)