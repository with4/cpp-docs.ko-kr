---
title: 'multiset:: insert (STL/CLR) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::multiset::insert
dev_langs:
- C++
helpviewer_keywords:
- insert member [STL/CLR]
ms.assetid: 7a3b1cc8-ec60-4ed0-ace5-46cb5872e6e7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: ed7be7302b1dcef069dc1e786e59e87755366613
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="multisetinsert-stlclr"></a>multiset::insert(STL/CLR)
요소를 추가합니다.  
  
## <a name="syntax"></a>구문  
  
```  
iterator insert(value_type val);  
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
  
 첫 번째 멤버 함수는 값을 가진 요소를 삽입 `val`, 새로 삽입된 된 요소를 지정 하는 반복기를 반환 합니다. 단일 요소를 삽입 하려면 사용 합니다.  
  
 두 번째 멤버 함수는 값을 가진 요소를 삽입 `val`를 사용 하 여 `where` (성능을 향상 시키기) 힌트로 새로 삽입된 된 요소를 지정 하는 반복기를 반환 합니다. 알고 있는 요소에 인접 한 될 수 있는 단일 요소를 삽입 하려면 사용 합니다.  
  
 세 번째 멤버 함수는 시퀀스를 삽입 [`first`, `last`). 다른 시퀀스에서 복사 된 0 개 이상의 요소를 삽입 하려면 사용 합니다.  
  
 로 지정 된 시퀀스를 삽입 하는 네 번째 멤버 함수는 `right`합니다. 열거자에서 설명 하는 시퀀스를 삽입 하려면 사용 합니다.  
  
 제어 된 시퀀스의 요소 수 로그 비례 하는 시간을 사용 하는 각 요소를 삽입 합니다. 그러나 삽입 발생할 수 있습니다 분할 상환된 상수 시간에 삽입 지점에 인접 하는 요소를 지정 하는 힌트를 제공 합니다.  
  
## <a name="example"></a>예제  
  
```  
// cliext_multiset_insert.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert a single value, unique and duplicate   
    System::Console::WriteLine("insert(L'x') = {0}",   
        *c1.insert(L'x'));   
  
    System::Console::WriteLine("insert(L'b') = {0}",   
        *c1.insert(L'b'));   
  
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert a single value with hint   
    System::Console::WriteLine("insert(begin(), L'y') = {0}",   
        *c1.insert(c1.begin(), L'y'));   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert an iterator range   
    Mymultiset c2;   
    Mymultiset::iterator it = c1.end();   
    c2.insert(c1.begin(), --it);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert an enumeration   
    Mymultiset c3;   
    c3.insert(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c1);   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
insert(L'x') = x  
insert(L'b') = b  
 a b b c x  
insert(begin(), L'y') = y  
 a b b c x y  
 a b b c x  
 a b b c x y  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/set >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [multiset(STL/CLR)](../dotnet/multiset-stl-clr.md)