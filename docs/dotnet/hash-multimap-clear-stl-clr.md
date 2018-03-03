---
title: 'hash_multimap:: clear (STL/CLR) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::hash_multimap::clear
dev_langs:
- C++
helpviewer_keywords:
- clear member [STL/CLR]
ms.assetid: 8ad99f08-93b3-42b7-be07-f9a8ec556554
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 581579af2aae110bcf36166c58d671b1a27dfd71
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="hashmultimapclear-stlclr"></a>hash_multimap::clear(STL/CLR)
모든 요소를 제거합니다.  
  
## <a name="syntax"></a>구문  
  
```  
void clear();  
```  
  
## <a name="remarks"></a>설명  
 멤버 함수 시그니처 [hash_multimap:: erase (STL/CLR)](../dotnet/hash-multimap-erase-stl-clr.md) `(` [hash_multimap:: begin (STL/CLR)](../dotnet/hash-multimap-begin-stl-clr.md) `(),` [hash_multimap:: end (STL/CLR) ](../dotnet/hash-multimap-end-stl-clr.md)`())`. 제어 되는 시퀀스 비어 있는지 확인 하려면 사용 합니다.  
  
## <a name="example"></a>예  
  
```  
// cliext_hash_multimap_clear.cpp   
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
  
// clear the container and reinspect   
    c1.clear();   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
    c1.insert(Myhash_multimap::make_value(L'a', 1));   
    c1.insert(Myhash_multimap::make_value(L'b', 2));   
  
// display contents " [a 1] [b 2]"   
    for each (Myhash_multimap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
    c1.clear();   
    System::Console::WriteLine("size() = {0}", c1.size());   
    return (0);   
    }  
  
```  
  
```Output  
 [a 1] [b 2] [c 3]  
size() = 0  
 [a 1] [b 2]  
size() = 0  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/hash_map >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [hash_multimap (STL/CLR)](../dotnet/hash-multimap-stl-clr.md)   
 [hash_multimap::erase(STL/CLR)](../dotnet/hash-multimap-erase-stl-clr.md)