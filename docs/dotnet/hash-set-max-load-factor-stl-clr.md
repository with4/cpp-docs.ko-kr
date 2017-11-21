---
title: 'hash_set:: max_load_factor (STL/CLR) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::hash_set::max_load_factor
dev_langs: C++
helpviewer_keywords: max_load_factor member [STL/CLR]
ms.assetid: 9aef46b1-e7c2-488c-a219-77c1c0de6dc4
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 82f1208969cc10b8cb5a3baa6f866291ce6380bf
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="hashsetmaxloadfactor-stlclr"></a>hash_set::max_load_factor(STL/CLR)
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
// cliext_hash_set_max_load_factor.cpp   
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
 a b c  
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
 **헤더:** \<cliext/hash_set >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [hash_set (STL/CLR)](../dotnet/hash-set-stl-clr.md)   
 [hash_set:: bucket_count (STL/CLR)](../dotnet/hash-set-bucket-count-stl-clr.md)   
 [hash_set:: load_factor (STL/CLR)](../dotnet/hash-set-load-factor-stl-clr.md)   
 [hash_set::rehash(STL/CLR)](../dotnet/hash-set-rehash-stl-clr.md)