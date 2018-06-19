---
title: 'hash_multiset:: count (STL/CLR) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::hash_multiset::count
dev_langs:
- C++
helpviewer_keywords:
- count member [STL/CLR]
ms.assetid: 2b31e6b6-3f2c-4042-a06d-90d3074aad43
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 9de95e69c64c808c53ddb4a946ee18cebeebdeba
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33132039"
---
# <a name="hashmultisetcount-stlclr"></a>hash_multiset::count(STL/CLR)
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
  
## <a name="example"></a>예제  
  
```  
// cliext_hash_multiset_count.cpp   
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
  
    System::Console::WriteLine("count(L'A') = {0}", c1.count(L'A'));   
    System::Console::WriteLine("count(L'b') = {0}", c1.count(L'b'));   
    System::Console::WriteLine("count(L'C') = {0}", c1.count(L'C'));   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
count(L'A') = 0  
count(L'b') = 1  
count(L'C') = 0  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/hash_set >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [hash_multiset (STL/CLR)](../dotnet/hash-multiset-stl-clr.md)   
 [hash_multiset::equal_range(STL/CLR)](../dotnet/hash-multiset-equal-range-stl-clr.md)