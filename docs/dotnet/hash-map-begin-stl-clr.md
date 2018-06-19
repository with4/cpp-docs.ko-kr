---
title: 'hash_map:: begin (STL/CLR) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::hash_map::begin
dev_langs:
- C++
helpviewer_keywords:
- begin member [STL/CLR]
ms.assetid: b2ff4605-ac37-4456-8299-b3bcccdbe45a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 898f97df34b48dbaa3b706042d5663038faf65c7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33108402"
---
# <a name="hashmapbegin-stlclr"></a>hash_map::begin(STL/CLR)
제어되는 시퀀스의 시작을 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
iterator begin();  
```  
  
## <a name="remarks"></a>설명  
 멤버 함수는 제어 되는 시퀀스 또는 빈 시퀀스의 끝 바로 다음의 첫 번째 요소를 지정 하는 양방향 반복기를 반환 합니다. 지정 하는 반복기를 사용 하면는 `current` 제어 된 시퀀스의 길이가 변경 하는 경우의 상태 제어 된 시퀀스의 시작 부분을 변경할 수 있습니다.  
  
## <a name="example"></a>예제  
  
```  
// cliext_hash_map_begin.cpp   
// compile with: /clr   
#include <cliext/hash_map>   
  
typedef cliext::hash_map<wchar_t, int> Myhash_map;   
int main()   
    {   
    Myhash_map c1;   
    c1.insert(Myhash_map::make_value(L'a', 1));   
    c1.insert(Myhash_map::make_value(L'b', 2));   
    c1.insert(Myhash_map::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Myhash_map::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// inspect first two items   
    Myhash_map::iterator it = c1.begin();   
    System::Console::WriteLine("*begin() = [{0} {1}]",   
        it->first, it->second);   
    ++it;   
    System::Console::WriteLine("*++begin() = [{0} {1}]",   
        it->first, it->second);   
    return (0);   
    }  
  
```  
  
```Output  
 [a 1] [b 2] [c 3]  
*begin() = [a 1]  
*++begin() = [b 2]  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/hash_map >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [hash_map (STL/CLR)](../dotnet/hash-map-stl-clr.md)   
 [hash_map::end(STL/CLR)](../dotnet/hash-map-end-stl-clr.md)