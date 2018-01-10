---
title: 'list:: insert (STL/CLR) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::list::insert
dev_langs: C++
helpviewer_keywords: insert member [STL/CLR]
ms.assetid: 399ed30f-6b76-41a8-b180-6070e3ca1c68
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: ca57eb33999754dc44df0f49cf1089e137fd2d1d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="listinsert-stlclr"></a>list::insert(STL/CLR)
지정된 된 위치에 요소를 추가합니다.  
  
## <a name="syntax"></a>구문  
  
```  
iterator insert(iterator where, value_type val);  
void insert(iterator where, size_type count, value_type val);  
template<typename InIt>  
    void insert(iterator where, InIt first, InIt last);  
void insert(iterator where,  
    System::Collections::Generic::IEnumerable<Value>^ right);  
```  
  
#### <a name="parameters"></a>매개 변수  
 count  
 삽입할 요소의 수입니다.  
  
 첫 번째  
 삽입할 범위의의 시작입니다.  
  
 last  
 삽입할 범위의 끝입니다.  
  
 오른쪽  
 삽입 하는 열거형입니다.  
  
 val  
 삽입할 요소의 값입니다.  
  
 형식에 대한 설명  
 앞에 삽입 하는 컨테이너의 위치입니다.  
  
## <a name="remarks"></a>설명  
 가 가리키는 요소 앞의 삽입, 함수는 멤버의 각 `where` 제어 된 시퀀스의 시퀀스는 나머지 피연산자에서 지정 합니다.  
  
 첫 번째 멤버 함수는 값을 가진 요소를 삽입 `val` 새로 삽입된 된 요소를 지정 하는 반복기를 반환 합니다. 반복기에서 지정 하는 장소 하기 전에 단일 요소를 삽입 하려면 사용 합니다.  
  
 두 번째 멤버 함수는 `val` 값의 `count` 요소 반복을 삽입합니다. 같은 값의 모든 복사본 인 0 개 이상의 연속 요소를 삽입 하려면 사용 합니다.  
  
 `InIt`가 정수 형식이면 세 번째 멤버 함수는 `insert(where, (size_type)first, (value_type)last)`와 동일하게 동작합니다. 시퀀스를 삽입, 그렇지 않으면 [`first`, `last`). 다른 시퀀스에서 복사 된 0 개 이상의 연속 요소를 삽입 하려면 사용 합니다.  
  
 로 지정 된 시퀀스를 삽입 하는 네 번째 멤버 함수는 `right`합니다. 열거자에서 설명 하는 시퀀스를 삽입 하려면 사용 합니다.  
  
 단일 요소를 삽입할 경우에 요소 복사본의 수는 삽입 지점와 떨어진 끝 시퀀스의 요소 수에 비례 합니다. (시퀀스의 끝에 하나 이상의 요소를 삽입할 경우 요소 복사본이 발생 합니다.) 경우 `InIt` 입력 반복기, 세 번째 멤버 함수는 시퀀스의 각 요소에 대 한 단일 삽입을 효과적으로 수행 합니다. 삽입할 때 그렇지 `N` 요소, 요소 복사본 수에 비례는 `N` 삽입 포인터와 떨어진 시퀀스의 끝 간 요소 수를 더한 값입니다.  
  
## <a name="example"></a>예  
  
```  
// cliext_list_insert.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert a single value using iterator   
    cliext::list<wchar_t>::iterator it = c1.begin();   
    System::Console::WriteLine("insert(begin()+1, L'x') = {0}",   
        *c1.insert(++it, L'x'));   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert a repetition of values   
    cliext::list<wchar_t> c2;   
    c2.insert(c2.begin(), 2, L'y');   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert an iterator range   
    it = c1.end();   
    c2.insert(c2.end(), c1.begin(), --it);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert an enumeration   
    c2.insert(c2.begin(),   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c1);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert a single value using index   
    it = c2.begin();   
    ++it, ++it, ++it;   
    c2.insert(it, L'z');   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
insert(begin()+1, L'x') = x  
 a x b c  
 y y  
 y y a x b  
 a x b c y y a x b  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/목록 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [list (STL/CLR)](../dotnet/list-stl-clr.md)   
 [list::assign(STL/CLR)](../dotnet/list-assign-stl-clr.md)