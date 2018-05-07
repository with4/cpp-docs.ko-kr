---
title: 'hash_multimap:: max_load_factor (STL/CLR) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::hash_multimap::max_load_factor
dev_langs:
- C++
helpviewer_keywords:
- max_load_factor member [STL/CLR]
ms.assetid: acea6293-9c6f-4c5e-a9a3-998e755ba1fd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: c075ca386e7a08e0081a73c1b83d658a9e0c02d5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="hashmultimapmaxloadfactor-stlclr"></a>hash_multimap::max_load_factor(STL/CLR)
버킷당 최대 요소 수를 가져오거나 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
float max_load_factor();  
void max_load_factor(float new_factor);  
```  
  
#### <a name="parameters"></a>매개 변수  
 new_factor  
 새 최대값을 저장 하 게 하는 요소를 로드 합니다.  
  
## <a name="remarks"></a>설명  
 첫 번째 멤버 함수는 현재 저장 된 최대 로드 비율을 반환합니다. 최대 평균 버킷 크기를 확인 하려면 사용 합니다.  
  
 와 저장소 최대 로드 비율을 대체 하는 두 번째 멤버 함수 `new_factor`합니다. 자동 해싱하여 후속 삽입 될 때까지 발생합니다.  
  
## <a name="example"></a>예제  
  
```  
// cliext_hash_multimap_max_load_factor.cpp   
// compile with: /clr   
#include <cliext/hash_map>   
  
typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;   
int main()   
    {   
    Myhash_multimap c1 = gcnew Myhash_multimap;   
    c1.insert(Myhash_multimap::make_value(L'a', 1));   
    c1.insert(Myhash_multimap::make_value(L'b', 2));   
    c1.insert(Myhash_multimap::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Myhash_multimap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// inspect current parameters   
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());   
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());   
    System::Console::WriteLine("max_load_factor() = {0}",   
        c1.max_load_factor());   
    System::Console::WriteLine();   
  
// change max_load_factor and redisplay   
    c1.max_load_factor(0.25f);   
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());   
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());   
    System::Console::WriteLine("max_load_factor() = {0}",   
        c1.max_load_factor());   
    System::Console::WriteLine();   
  
// rehash and redisplay   
    c1.rehash(100);   
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());   
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());   
    System::Console::WriteLine("max_load_factor() = {0}",   
        c1.max_load_factor());   
    return (0);   
    }  
  
```  
  
```Output  
 [a 1] [b 2] [c 3]  
bucket_count() = 16  
load_factor() = 0.1875  
max_load_factor() = 4  
  
bucket_count() = 16  
load_factor() = 0.1875  
max_load_factor() = 0.25  
  
bucket_count() = 128  
load_factor() = 0.0234375  
max_load_factor() = 0.25  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/hash_map >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [hash_multimap (STL/CLR)](../dotnet/hash-multimap-stl-clr.md)   
 [hash_multimap:: bucket_count (STL/CLR)](../dotnet/hash-multimap-bucket-count-stl-clr.md)   
 [hash_multimap:: load_factor (STL/CLR)](../dotnet/hash-multimap-load-factor-stl-clr.md)   
 [hash_multimap::rehash(STL/CLR)](../dotnet/hash-multimap-rehash-stl-clr.md)