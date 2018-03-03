---
title: 'hash_multiset:: iterator (STL/CLR) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::hash_multiset::iterator
dev_langs:
- C++
helpviewer_keywords:
- iterator member [STL/CLR]
ms.assetid: 47c565d9-2bbc-45d8-801f-cab43ed45ab4
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: c86481bf178ebefbfbfaea9141406a8661f79d35
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="hashmultisetiterator-stlclr"></a>hash_multiset::iterator(STL/CLR)
제어되는 시퀀스에 대한 반복기의 형식입니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef T1 iterator;  
```  
  
## <a name="remarks"></a>설명  
 이 형식은 지정 되지 않은 형식의 개체를 설명 `T1` 제어 되는 시퀀스에 대 한 양방향 반복기로 사용할 수 있는 합니다.  
  
## <a name="example"></a>예  
  
```  
// cliext_hash_multiset_iterator.cpp   
// compile with: /clr   
#include <cliext/hash_set>   
  
typedef cliext::hash_multiset<wchar_t> Myhash_multiset;   
int main()   
    {   
    Myhash_multiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display contents " a b c"   
    Myhash_multiset::iterator it = c1.begin();   
    for (; it != c1.end(); ++it)   
        System::Console::Write(" {0}", *it);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/hash_set >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [hash_multiset (STL/CLR)](../dotnet/hash-multiset-stl-clr.md)   
 [hash_multiset::const_iterator(STL/CLR)](../dotnet/hash-multiset-const-iterator-stl-clr.md)