---
title: 'map:: map (STL/CLR) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::map::map
dev_langs:
- C++
helpviewer_keywords:
- map member [STL/CLR]
ms.assetid: c91f699a-4742-4859-b2b3-c2a01a750bea
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 320c3c4223996826fe1e7b3104540baddd82da5a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="mapmap-stlclr"></a>map::map(STL/CLR)
컨테이너 개체를 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```  
map();  
explicit map(key_compare^ pred);  
map(map<Key, Mapped>% right);  
map(map<Key, Mapped>^ right);  
template<typename InIter>  
    mapmap(InIter first, InIter last);  
template<typename InIter>  
    map(InIter first, InIter last,  
        key_compare^ pred);  
map(System::Collections::Generic::IEnumerable<GValue>^ right);  
map(System::Collections::Generic::IEnumerable<GValue>^ right,  
    key_compare^ pred);  
```  
  
#### <a name="parameters"></a>매개 변수  
 첫 번째  
 삽입할 범위의의 시작입니다.  
  
 last  
 삽입할 범위의 끝입니다.  
  
 pred  
 제어 되는 시퀀스에 대 한 조건자를 정렬 합니다.  
  
 오른쪽  
 삽입할 개체 또는 범위입니다.  
  
## <a name="remarks"></a>설명  
 생성자:  
  
 `map();`  
  
 기본 조건자를 정렬 된 요소가 없는 제어 되는 시퀀스를 초기화 `key_compare()`합니다. 기본 조건자를 정렬 된는 빈 초기 제어 시퀀스를 지정 하려면 사용 합니다.  
  
 생성자:  
  
 `explicit map(key_compare^ pred);`  
  
 정렬 조건자가 있는 요소가 없는 제어 되는 시퀀스를 초기화 `pred`합니다. 지정 된 정렬 조건부와 함께 빈 초기 제어 시퀀스를 지정 하려면 사용 합니다.  
  
 생성자:  
  
 `map(map<Key, Mapped>% right);`  
  
 순서와 제어 된 시퀀스를 초기화 합니다. [`right.begin()`, `right.end()`), 조건자 순서 기본값입니다. 지도 개체에 의해 제어 되는 시퀀스의 복사본 인는 초기 제어 시퀀스를 지정 하려면 사용할 `right`, 조건자 순서 기본값입니다.  
  
 생성자:  
  
 `map(map<Key, Mapped>^ right);`  
  
 순서와 제어 된 시퀀스를 초기화 합니다. [`right->begin()`, `right->end()`), 조건자 순서 기본값입니다. 지도 개체에 의해 제어 되는 시퀀스의 복사본 인는 초기 제어 시퀀스를 지정 하려면 사용할 `right`, 조건자 순서 기본값입니다.  
  
 생성자:  
  
 `template<typename InIter> map(InIter first, InIter last);`  
  
 순서와 제어 된 시퀀스를 초기화 합니다. [`first`, `last`), 조건자 순서 기본값입니다. 기본 조건자를 정렬 된 제어 되는 다른 시퀀스의 복사본을 확인을 사용 합니다.  
  
 생성자:  
  
 `template<typename InIter> map(InIter first, InIter last, key_compare^ pred);`  
  
 순서와 제어 된 시퀀스를 초기화 합니다. [`first`, `last`), 정렬 조건부와 함께 `pred`합니다. 제어 되는 시퀀스의 사본을 지정 된 정렬 조건부와 함께 다른 시퀀스를 사용 합니다.  
  
 생성자:  
  
 `map(System::Collections::Generic::IEnumerable<Key>^ right);`  
  
 열거자에 지정 된 시퀀스와 제어 된 시퀀스를 초기화 `right`, 조건자 순서 기본값입니다. 제어 되는 시퀀스의 사본을 설명 하는 열거자에 따라 기본 조건자를 정렬 하는 다른 시퀀스를 사용 합니다.  
  
 생성자:  
  
 `map(System::Collections::Generic::IEnumerable<Key>^ right, key_compare^ pred);`  
  
 열거자에 지정 된 시퀀스와 제어 된 시퀀스를 초기화 `right`, 정렬 조건부와 함께 `pred`합니다. 제어 되는 시퀀스에서 지정 된 정렬 조건부와 함께 열거자를 설명 하는 다른 시퀀스의 복사본 수 있도록 사용 합니다.  
  
## <a name="example"></a>예  
  
```cpp  
// cliext_map_construct.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::map<wchar_t, int> Mymap;   
int main()   
    {   
// construct an empty container   
    Mymap c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
    c1.insert(Mymap::make_value(L'a', 1));   
    c1.insert(Mymap::make_value(L'b', 2));   
    c1.insert(Mymap::make_value(L'c', 3));   
    for each (Mymap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct with an ordering rule   
    Mymap c2 = cliext::greater_equal<wchar_t>();   
    System::Console::WriteLine("size() = {0}", c2.size());   
  
    c2.insert(c1.begin(), c1.end());   
    for each (Mymap::value_type elem in c2)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct with an iterator range   
    Mymap c3(c1.begin(), c1.end());   
    for each (Mymap::value_type elem in c3)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct with an iterator range and an ordering rule   
    Mymap c4(c1.begin(), c1.end(),   
        cliext::greater_equal<wchar_t>());   
    for each (Mymap::value_type elem in c4)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct with an enumeration   
    Mymap c5(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<   
            Mymap::value_type>^)%c3);   
    for each (Mymap::value_type elem in c5)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct with an enumeration and an ordering rule   
    Mymap c6(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<   
            Mymap::value_type>^)%c3,   
                cliext::greater_equal<wchar_t>());   
    for each (Mymap::value_type elem in c6)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    Mymap c7(c4);   
    for each (Mymap::value_type elem in c7)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct by copying a container handle   
    Mymap c8(%c3);   
    for each (Mymap::value_type elem in c8)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
size() = 0  
 [a 1] [b 2] [c 3]  
size() = 0  
 [c 3] [b 2] [a 1]  
 [a 1] [b 2] [c 3]  
 [c 3] [b 2] [a 1]  
 [a 1] [b 2] [c 3]  
 [c 3] [b 2] [a 1]  
 [c 3] [b 2] [a 1]  
 [a 1] [b 2] [c 3]  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/매핑 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [map (STL/CLR)](../dotnet/map-stl-clr.md)   
 [map:: generic_container (STL/CLR)](../dotnet/map-generic-container-stl-clr.md)   
 [map::operator=(STL/CLR)](../dotnet/map-operator-assign-stl-clr.md)