---
title: 'map:: equal_range (STL/CLR) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::map::equal_range
dev_langs:
- C++
helpviewer_keywords:
- equal_range member [STL/CLR]
ms.assetid: c0d7409c-344d-4102-99c4-aeab8643a073
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 9769b40cc312e794e711a8ddab83eada76e835bc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="mapequalrange-stlclr"></a>map::equal_range(STL/CLR)
지정된 키와 일치하는 범위를 찾습니다.  
  
## <a name="syntax"></a>구문  
  
```  
cliext::pair<iterator, iterator> equal_range(key_type key);  
```  
  
#### <a name="parameters"></a>매개 변수  
 key  
 검색할 키 값입니다.  
  
## <a name="remarks"></a>설명  
 멤버 함수는 한 쌍의 반복기를 반환 `cliext::pair<iterator, iterator>(` [map:: lower_bound (STL/CLR)](../dotnet/map-lower-bound-stl-clr.md) `(key),` [map:: upper_bound (STL/CLR)](../dotnet/map-upper-bound-stl-clr.md)`(key))`합니다. 지정된 된 키와 일치 하는 제어 된 시퀀스의 현재 요소의 범위를 확인 하려면 사용 합니다.  
  
## <a name="example"></a>예제  
  
```  
// cliext_map_equal_range.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::map<wchar_t, int> Mymap;   
typedef Mymap::pair_iter_iter Pairii;   
int main()   
    {   
    Mymap c1;   
    c1.insert(Mymap::make_value(L'a', 1));   
    c1.insert(Mymap::make_value(L'b', 2));   
    c1.insert(Mymap::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Mymap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// display results of failed search   
    Pairii pair1 = c1.equal_range(L'x');   
    System::Console::WriteLine("equal_range(L'x') empty = {0}",   
        pair1.first == pair1.second);   
  
// display results of successful search   
    pair1 = c1.equal_range(L'b');   
    for (; pair1.first != pair1.second; ++pair1.first)   
        System::Console::Write(" [{0} {1}]",   
            pair1.first->first, pair1.first->second);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
 [a 1] [b 2] [c 3]  
equal_range(L'x') empty = True  
 [b 2]  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/매핑 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [map (STL/CLR)](../dotnet/map-stl-clr.md)   
 [map:: count (STL/CLR)](../dotnet/map-count-stl-clr.md)   
 [map:: find (STL/CLR)](../dotnet/map-find-stl-clr.md)   
 [map:: lower_bound (STL/CLR)](../dotnet/map-lower-bound-stl-clr.md)   
 [map::upper_bound(STL/CLR)](../dotnet/map-upper-bound-stl-clr.md)