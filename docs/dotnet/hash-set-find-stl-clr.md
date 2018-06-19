---
title: 'hash_set:: find (STL/CLR) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::hash_set::find
dev_langs:
- C++
helpviewer_keywords:
- find member [STL/CLR]
ms.assetid: 758b7438-ef15-4af0-8001-a1126d5e9a9e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 63a8be1bc59d6c2b9cc2128295a9e39dea14cf84
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33126915"
---
# <a name="hashsetfind-stlclr"></a>hash_set::find(STL/CLR)
지정된 키와 일치하는 요소를 찾습니다.  
  
## <a name="syntax"></a>구문  
  
```  
iterator find(key_type key);  
```  
  
#### <a name="parameters"></a>매개 변수  
 key  
 검색할 키 값입니다.  
  
## <a name="remarks"></a>설명  
 동일 하 게 정렬 된 제어 되는 시퀀스에 요소가 하나 이상 있으면 `key`, 이러한 요소 중 하나를 지정 하는 반복기를 반환 하는 멤버 함수, 그렇지 않으면 반환 [hash_set:: end (STL/CLR)](../dotnet/hash-set-end-stl-clr.md) `()`. 지정된 된 키와 일치 하는 제어 된 시퀀스의 현재 요소를 찾을 수 사용 합니다.  
  
## <a name="example"></a>예제  
  
```  
// cliext_hash_set_find.cpp   
// compile with: /clr   
#include <cliext/hash_set>   
  
typedef cliext::hash_set<wchar_t> Myhash_set;   
int main()   
    {   
    Myhash_set c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("find {0} = {1}",   
        L'A', c1.find(L'A') != c1.end());   
    System::Console::WriteLine("find {0} = {1}",   
        L'b', *c1.find(L'b'));   
    System::Console::WriteLine("find {0} = {1}",   
        L'C', c1.find(L'C') != c1.end());   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
find A = False  
find b = b  
find C = False  
```  
  
## <a name="description"></a>설명  
 `find` 발견 하는 여러 가지 요소는 보장 하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/hash_set >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [hash_set (STL/CLR)](../dotnet/hash-set-stl-clr.md)   
 [hash_set:: equal_range (STL/CLR)](../dotnet/hash-set-equal-range-stl-clr.md)   
 [hash_set:: lower_bound (STL/CLR)](../dotnet/hash-set-lower-bound-stl-clr.md)   
 [hash_set::upper_bound(STL/CLR)](../dotnet/hash-set-upper-bound-stl-clr.md)