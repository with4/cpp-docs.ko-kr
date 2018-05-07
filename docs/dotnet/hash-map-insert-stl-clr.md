---
title: 'hash_map:: insert (STL/CLR) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::hash_map::insert
dev_langs:
- C++
helpviewer_keywords:
- insert member [STL/CLR]
ms.assetid: 52926ec7-ad4e-4791-a043-46136ee40a69
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 89f6000f7950aa55b4b547def13dcb9cfe34012c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="hashmapinsert-stlclr"></a>hash_map::insert(STL/CLR)
요소를 추가합니다.  
  
## <a name="syntax"></a>구문  
  
```  
cliext::pair<iterator, bool> insert(value_type val);  
iterator insert(iterator where, value_type val);  
template<typename InIter>  
    void insert(InIter first, InIter last);  
void insert(System::Collections::Generic::IEnumerable<value_type>^ right);  
```  
  
#### <a name="parameters"></a>매개 변수  
 첫 번째  
 삽입할 범위의의 시작입니다.  
  
 last  
 삽입할 범위의 끝입니다.  
  
 오른쪽  
 삽입 하는 열거형입니다.  
  
 val  
 삽입할 키 값입니다.  
  
 형식에 대한 설명  
 (힌트에만 해당)를 삽입할 컨테이너의 위치입니다.  
  
## <a name="remarks"></a>설명  
 각 멤버 함수는 나머지 피연산자에서 지정 된 시퀀스를 삽입 합니다.  
  
 첫 번째 멤버 함수는 값을 가진 요소를 삽입할 노력 `val`, 한 쌍의 값을 반환 하 고 `X`합니다. 경우 `X.second` 가 true 이면 `X.first` 새로 삽입된 된 요소를 지정 고, 그렇지 않으면 `X.first` 해당 키와 요소를 지정 순서 이미 존재 하 고 새 요소가 삽입 됩니다. 단일 요소를 삽입 하려면 사용 합니다.  
  
 두 번째 멤버 함수는 값을 가진 요소를 삽입 `val`를 사용 하 여 `where` (성능을 향상 시키기) 힌트로 새로 삽입된 된 요소를 지정 하는 반복기를 반환 합니다. 알고 있는 요소에 인접 한 될 수 있는 단일 요소를 삽입 하려면 사용 합니다.  
  
 세 번째 멤버 함수는 시퀀스를 삽입 [`first`, `last`). 다른 시퀀스에서 복사 된 0 개 이상의 요소를 삽입 하려면 사용 합니다.  
  
 로 지정 된 시퀀스를 삽입 하는 네 번째 멤버 함수는 `right`합니다. 열거자에서 설명 하는 시퀀스를 삽입 하려면 사용 합니다.  
  
 제어 된 시퀀스의 요소 수 로그 비례 하는 시간을 사용 하는 각 요소를 삽입 합니다. 그러나 삽입 발생할 수 있습니다 분할 상환된 상수 시간에 삽입 지점에 인접 하는 요소를 지정 하는 힌트를 제공 합니다.  
  
## <a name="example"></a>예제  
  
```  
// cliext_hash_map_insert.cpp   
// compile with: /clr   
#include <cliext/hash_map>   
  
typedef cliext::hash_map<wchar_t, int> Myhash_map;   
typedef Myhash_map::pair_iter_bool Pairib;   
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
  
// insert a single value, unique and duplicate   
    Pairib pair1 =   
        c1.insert(Myhash_map::make_value(L'x', 24));   
    System::Console::WriteLine("insert([L'x' 24]) = [{0} {1}] {2}",   
        pair1.first->first, pair1.first->second, pair1.second);   
  
    pair1 = c1.insert(Myhash_map::make_value(L'b', 2));   
    System::Console::WriteLine("insert([L'b' 2]) = [{0} {1}] {2}",   
        pair1.first->first, pair1.first->second, pair1.second);   
  
    for each (Myhash_map::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// insert a single value with hint   
    Myhash_map::iterator it =   
        c1.insert(c1.begin(), Myhash_map::make_value(L'y', 25));   
    System::Console::WriteLine("insert(begin(), [L'y' 25]) = [{0} {1}]",   
        it->first, it->second);   
    for each (Myhash_map::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// insert an iterator range   
    Myhash_map c2;   
    it = c1.end();   
    c2.insert(c1.begin(), --it);   
    for each (Myhash_map::value_type elem in c2)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// insert an enumeration   
    Myhash_map c3;   
    c3.insert(   // NOTE: cast is not needed   
        (System::Collections::Generic::   
            IEnumerable<Myhash_map::value_type>^)%c1);   
    for each (Myhash_map::value_type elem in c3)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
 [a 1] [b 2] [c 3]  
insert([L'x' 24]) = [x 24] True  
insert([L'b' 2]) = [b 2] False  
 [a 1] [b 2] [c 3] [x 24]  
insert(begin(), [L'y' 25]) = [y 25]  
 [a 1] [b 2] [c 3] [x 24] [y 25]  
 [a 1] [b 2] [c 3] [x 24]  
 [a 1] [b 2] [c 3] [x 24] [y 25]  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/hash_map >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [hash_map(STL/CLR)](../dotnet/hash-map-stl-clr.md)