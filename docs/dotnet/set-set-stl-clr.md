---
title: 'set:: set (STL/CLR) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::set::set
dev_langs:
- C++
helpviewer_keywords:
- set member [STL/CLR]
ms.assetid: 0cce8501-92ed-431c-b711-14e0b7be7375
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 381473ceebe696bce549732de6a738f733161403
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="setset-stlclr"></a>set::set(STL/CLR)
컨테이너 개체를 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```  
set();  
explicit set(key_compare^ pred);  
set(set<Key>% right);  
set(set<Key>^ right);  
template<typename InIter>  
    setset(InIter first, InIter last);  
template<typename InIter>  
    set(InIter first, InIter last,  
        key_compare^ pred);  
set(System::Collections::Generic::IEnumerable<GValue>^ right);  
set(System::Collections::Generic::IEnumerable<GValue>^ right,  
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
  
 `set();`  
  
 기본 조건자를 정렬 된 요소가 없는 제어 되는 시퀀스를 초기화 `key_compare()`합니다. 기본 조건자를 정렬 된는 빈 초기 제어 시퀀스를 지정 하려면 사용 합니다.  
  
 생성자:  
  
 `explicit set(key_compare^ pred);`  
  
 정렬 조건자가 있는 요소가 없는 제어 되는 시퀀스를 초기화 `pred`합니다. 지정 된 정렬 조건부와 함께 빈 초기 제어 시퀀스를 지정 하려면 사용 합니다.  
  
 생성자:  
  
 `set(set<Key>% right);`  
  
 순서와 제어 된 시퀀스를 초기화 합니다. [`right.begin()`, `right.end()`), 조건자 순서 기본값입니다. 집합 개체에 의해 제어 되는 시퀀스의 복사본 인는 초기 제어 시퀀스를 지정 하려면 사용할 `right`, 조건자 순서 기본값입니다.  
  
 생성자:  
  
 `set(set<Key>^ right);`  
  
 순서와 제어 된 시퀀스를 초기화 합니다. [`right->begin()`, `right->end()`), 조건자 순서 기본값입니다. 집합 개체에 의해 제어 되는 시퀀스의 복사본 인는 초기 제어 시퀀스를 지정 하려면 사용할 `right`, 조건자 순서 기본값입니다.  
  
 생성자:  
  
 `template<typename InIter> set(InIter first, InIter last);`  
  
 순서와 제어 된 시퀀스를 초기화 합니다. [`first`, `last`), 조건자 순서 기본값입니다. 기본 조건자를 정렬 된 제어 되는 다른 시퀀스의 복사본을 확인을 사용 합니다.  
  
 생성자:  
  
 `template<typename InIter> set(InIter first, InIter last, key_compare^ pred);`  
  
 순서와 제어 된 시퀀스를 초기화 합니다. [`first`, `last`), 정렬 조건부와 함께 `pred`합니다. 제어 되는 시퀀스의 사본을 지정 된 정렬 조건부와 함께 다른 시퀀스를 사용 합니다.  
  
 생성자:  
  
 `set(System::Collections::Generic::IEnumerable<Key>^ right);`  
  
 열거자에 지정 된 시퀀스와 제어 된 시퀀스를 초기화 `right`, 조건자 순서 기본값입니다. 제어 되는 시퀀스의 사본을 설명 하는 열거자에 따라 기본 조건자를 정렬 하는 다른 시퀀스를 사용 합니다.  
  
 생성자:  
  
 `set(System::Collections::Generic::IEnumerable<Key>^ right, key_compare^ pred);`  
  
 열거자에 지정 된 시퀀스와 제어 된 시퀀스를 초기화 `right`, 정렬 조건부와 함께 `pred`합니다. 제어 되는 시퀀스에서 지정 된 정렬 조건부와 함께 열거자를 설명 하는 다른 시퀀스의 복사본 수 있도록 사용 합니다.  
  
## <a name="example"></a>예  
  
```cpp  
// cliext_set_construct.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::set<wchar_t> Myset;   
int main()   
    {   
// construct an empty container   
    Myset c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an ordering rule   
    Myset c2 = cliext::greater_equal<wchar_t>();   
    System::Console::WriteLine("size() = {0}", c2.size());   
  
    c2.insert(c1.begin(), c1.end());   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range   
    Myset c3(c1.begin(), c1.end());   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range and an ordering rule   
    Myset c4(c1.begin(), c1.end(),   
        cliext::greater_equal<wchar_t>());   
    for each (wchar_t elem in c4)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an enumeration   
    Myset c5(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3);   
    for each (wchar_t elem in c5)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an enumeration and an ordering rule   
    Myset c6(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3,   
            cliext::greater_equal<wchar_t>());   
    for each (wchar_t elem in c6)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct from a generic container   
    Myset c7(c4);   
    for each (wchar_t elem in c7)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    Myset c8(%c3);   
    for each (wchar_t elem in c8)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
size() = 0  
 a b c  
size() = 0  
 c b a  
 a b c  
 c b a  
 a b c  
 c b a  
 c b a  
 a b c  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/set >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [set (STL/CLR)](../dotnet/set-stl-clr.md)   
 [set:: generic_container (STL/CLR)](../dotnet/set-generic-container-stl-clr.md)   
 [set::operator=(STL/CLR)](../dotnet/set-operator-assign-stl-clr.md)