---
title: 'hash_multimap:: value_comp (STL/CLR) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::hash_multimap::value_comp
dev_langs:
- C++
helpviewer_keywords:
- value_comp member [STL/CLR]
ms.assetid: ec6108b8-a529-499b-bc7f-dce41f5b6175
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 9ef59cd84466f02d480e5c147e779bdcff0bbc90
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33134158"
---
# <a name="hashmultimapvaluecomp-stlclr"></a>hash_multimap::value_comp(STL/CLR)
두 요소 값에 대 한 순서 지정 대리자를 복사합니다.  
  
## <a name="syntax"></a>구문  
  
```  
value_compare^ value_comp();  
```  
  
## <a name="remarks"></a>설명  
 멤버 함수는 제어 되는 시퀀스를 정렬 하는 데 사용 되는 정렬 대리자를 반환 합니다. 두 요소 값 비교를 사용 합니다.  
  
## <a name="example"></a>예제  
  
```  
// cliext_hash_multimap_value_comp.cpp   
// compile with: /clr   
#include <cliext/hash_map>   
  
typedef cliext::hash_map<wchar_t, int> Myhash_multimap;   
int main()   
    {   
    Myhash_multimap c1;   
    Myhash_multimap::value_compare^ kcomp = c1.value_comp();   
  
    System::Console::WriteLine("compare([L'a', 1], [L'a', 1]) = {0}",   
        kcomp(Myhash_multimap::make_value(L'a', 1),   
            Myhash_multimap::make_value(L'a', 1)));   
    System::Console::WriteLine("compare([L'a', 1], [L'b', 2]) = {0}",   
        kcomp(Myhash_multimap::make_value(L'a', 1),   
            Myhash_multimap::make_value(L'b', 2)));   
    System::Console::WriteLine("compare([L'b', 2], [L'a', 1]) = {0}",   
        kcomp(Myhash_multimap::make_value(L'b', 2),   
            Myhash_multimap::make_value(L'a', 1)));   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
compare([L'a', 1], [L'a', 1]) = True  
compare([L'a', 1], [L'b', 2]) = True  
compare([L'b', 2], [L'a', 1]) = False  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/hash_map >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [hash_multimap (STL/CLR)](../dotnet/hash-multimap-stl-clr.md)   
 [hash_multimap:: value_compare (STL/CLR)](../dotnet/hash-multimap-value-compare-stl-clr.md)   
 [hash_multimap::value_type(STL/CLR)](../dotnet/hash-multimap-value-type-stl-clr.md)