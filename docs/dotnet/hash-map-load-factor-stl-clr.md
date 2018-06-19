---
title: 'hash_map:: load_factor (STL/CLR) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::hash_map::load_factor
dev_langs:
- C++
helpviewer_keywords:
- load_factor member [STL/CLR]
ms.assetid: e3a29b1f-ea20-4153-87b0-3935044d4d7a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 60dd0d577023f680a2535f34599ddb65b0af7656
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33110303"
---
# <a name="hashmaploadfactor-stlclr"></a>hash_map::load_factor(STL/CLR)
버킷당 평균 요소 수를 계산합니다.  
  
## <a name="syntax"></a>구문  
  
```  
float load_factor();  
```  
  
## <a name="remarks"></a>설명  
 멤버 함수는 반환 `(float)` [hash_map:: size (STL/CLR)](../dotnet/hash-map-size-stl-clr.md) `() /` [hash_map:: bucket_count (STL/CLR)](../dotnet/hash-map-bucket-count-stl-clr.md)`()`합니다. 평균 버킷 크기를 확인 하려면 사용 합니다.  
  
## <a name="example"></a>예제  
  
```  
// cliext_hash_map_load_factor.cpp   
// compile with: /clr   
#include <cliext/hash_map>   
  
typedef cliext::hash_map<wchar_t, int> Myhash_map;   
int main()   
    {   
    Myhash_map c1 = gcnew Myhash_map;   
    c1.insert(Myhash_map::make_value(L'a', 1));   
    c1.insert(Myhash_map::make_value(L'b', 2));   
    c1.insert(Myhash_map::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Myhash_map::value_type elem in c1)   
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
 [hash_map (STL/CLR)](../dotnet/hash-map-stl-clr.md)   
 [hash_map:: bucket_count (STL/CLR)](../dotnet/hash-map-bucket-count-stl-clr.md)   
 [hash_map::max_load_factor(STL/CLR)](../dotnet/hash-map-max-load-factor-stl-clr.md)