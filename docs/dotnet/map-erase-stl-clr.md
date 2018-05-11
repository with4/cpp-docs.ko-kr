---
title: 'map:: erase (STL/CLR) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::map::erase
dev_langs:
- C++
helpviewer_keywords:
- erase member [STL/CLR]
ms.assetid: a8fc88dd-a726-4a5b-bdf2-87743e98e687
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 0945f5ece27a6e4bb04322b607a288bdeeb84ad4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="maperase-stlclr"></a>map::erase(STL/CLR)
지정된 위치에 있는 요소를 제거합니다.  
  
## <a name="syntax"></a>구문  
  
```  
iterator erase(iterator where);  
iterator erase(iterator first, iterator last);  
bool erase(key_type key)  
```  
  
#### <a name="parameters"></a>매개 변수  
 첫 번째  
 범위를 지우려면의 시작입니다.  
  
 key  
 지우기 키 값입니다.  
  
 last  
 범위를 지우려면의 끝입니다.  
  
 형식에 대한 설명  
 지울 요소입니다.  
  
## <a name="remarks"></a>설명  
 가 가리키는 제어 된 시퀀스의 요소를 제거 하는 첫 번째 멤버 함수 `where`를 제거 하는 요소 뒤에 남은 첫 번째 요소를 지정 하는 반복기를 반환 하 고 또는 [map:: end (STL/CLR)](../dotnet/map-end-stl-clr.md) `()` 이러한 요소가 없을 경우. 단일 요소를 제거 하려면 사용 합니다.  
  
 범위에서 제어 된 시퀀스의 요소를 제거 하는 두 번째 멤버 함수 [`first`, `last`), 제거 된 요소 뒤에 남은 첫 번째 요소를 지정 하는 반복기를 반환 하거나 `end()` 요소가 없는 경우 있습니다. 0 개 이상의 연속 요소를 제거 하려면 사용 합니다.  
  
 해당 키가 동일 하 게 정렬 된 제어 된 시퀀스의 모든 요소를 제거 하는 세 번째 멤버 함수를 `key`, 제거 된 요소의 수를 반환 합니다. 제거 하 고 계산 된 지정 된 키와 일치 하는 모든 요소를 사용 합니다.  
  
 각 요소 삭제 시간이의 요소 수 로그에 비례 제어 된 시퀀스의 됩니다.  
  
## <a name="example"></a>예제  
  
```  
// cliext_map_erase.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::map<wchar_t, int> Mymap;   
int main()   
    {   
    cliext::map<wchar_t, int> c1;   
    c1.insert(cliext::map<wchar_t, int>::make_value(L'a', 1));   
    c1.insert(cliext::map<wchar_t, int>::make_value(L'b', 2));   
    c1.insert(cliext::map<wchar_t, int>::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (cliext::map<wchar_t, int>::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// erase an element and reinspect   
    cliext::map<wchar_t, int>::iterator it =   
        c1.erase(c1.begin());   
    System::Console::WriteLine("erase(begin()) = [{0} {1}]",   
        it->first, it->second);   
  
// add elements and display " b c d e"   
    c1.insert(cliext::map<wchar_t, int>::make_value(L'd', 4));   
    c1.insert(cliext::map<wchar_t, int>::make_value(L'e', 5));   
    for each (cliext::map<wchar_t, int>::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// erase all but end   
    it = c1.end();   
    it = c1.erase(c1.begin(), --it);   
    System::Console::WriteLine("erase(begin(), end()-1) = [{0} {1}]",   
        it->first, it->second);   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// erase end   
    System::Console::WriteLine("erase(L'x') = {0}", c1.erase(L'x'));   
    System::Console::WriteLine("erase(L'e') = {0}", c1.erase(L'e'));   
    return (0);   
    }  
  
```  
  
```Output  
 [a 1] [b 2] [c 3]  
erase(begin()) = [b 2]  
 [b 2] [c 3] [d 4] [e 5]  
erase(begin(), end()-1) = [e 5]  
size() = 1  
erase(L'x') = 0  
erase(L'e') = 1  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/매핑 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [map (STL/CLR)](../dotnet/map-stl-clr.md)   
 [map::clear(STL/CLR)](../dotnet/map-clear-stl-clr.md)