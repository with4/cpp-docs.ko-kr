---
title: 'hash_set:: const_reverse_iterator (STL/CLR) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::hash_set::const_reverse_iterator
dev_langs: C++
helpviewer_keywords: const_reverse_iterator member [STL/CLR]
ms.assetid: 26a58553-3c03-4ded-9d70-65dba6520184
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 24671a6cb24356bf39b5c16704a6d634a5346751
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="hashsetconstreverseiterator-stlclr"></a>hash_set::const_reverse_iterator(STL/CLR)
제어 되는 시퀀스에 대 한 상수 역방향 반복기의 형식입니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef T4 const_reverse_iterator;  
```  
  
## <a name="remarks"></a>설명  
 이 형식은 지정 되지 않은 형식의 개체를 설명 `T4` 제어 되는 시퀀스에 대 한 상수 역방향 반복기로 사용할 수 있는 합니다.  
  
## <a name="example"></a>예제  
  
```  
// cliext_hash_set_const_reverse_iterator.cpp   
// compile with: /clr   
#include <cliext/hash_set>   
  
typedef cliext::hash_set<wchar_t> Myhash_set;   
int main()   
    {   
    Myhash_set c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display contents " a b c" reversed   
    Myhash_set::const_reverse_iterator crit = c1.rbegin();   
    for (; crit != c1.rend(); ++crit)   
        System::Console::Write(" {0}", *crit);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
c b a  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/hash_set >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [hash_set (STL/CLR)](../dotnet/hash-set-stl-clr.md)   
 [hash_set::reverse_iterator(STL/CLR)](../dotnet/hash-set-reverse-iterator-stl-clr.md)