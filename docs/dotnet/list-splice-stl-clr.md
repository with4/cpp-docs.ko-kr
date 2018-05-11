---
title: 'list:: splice (STL/CLR) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::list::splice
dev_langs:
- C++
helpviewer_keywords:
- splice member [STL/CLR]
ms.assetid: ebc424b9-8341-4a88-b101-86d56324f5ac
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: e0c92faf6a4ec84e6ed65c58d02337038398d37e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="listsplice-stlclr"></a>list::splice(STL/CLR)
노드 간 링크 restitch 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
void splice(iterator where, list<Value>% right);  
void splice(iterator where, list<Value>% right,  
    iterator first);  
void splice(iterator where, list<Value>% right,  
    iterator first, iterator last);  
```  
  
#### <a name="parameters"></a>매개 변수  
 첫 번째  
 결합할 범위의 시작입니다.  
  
 last  
 결합할 범위의 끝입니다.  
  
 오른쪽  
 컨테이너에서 splice입니다.  
  
 형식에 대한 설명  
 Splice 전에 컨테이너에서 위치입니다.  
  
## <a name="remarks"></a>설명  
 첫 번째 멤버 함수에 의해 제어 시퀀스를 삽입 `right` 가리키는 제어 된 시퀀스의 요소 앞 `where`합니다. 또한 `right`에서 모든 요소를 제거합니다. (`%right` 같지 않아야 `this`.) 다른 파티션으로 splice 모두 하나의 목록에 사용 합니다.  
  
 가 가리키는 요소를 제거 하는 두 번째 멤버 함수 `first` 에서 제어 시퀀스의 `right` 가리키는 제어 된 시퀀스의 요소 앞에 삽입 `where`합니다. (경우 `where` `==` `first` `||` `where` `== ++first`, 변경 되지 않습니다.) 다른 파티션으로 하나의 목록의 단일 요소를 결합할 사용할 수 있습니다.  
  
 세 번째 멤버 함수에 지정 된 하위 범위를 삽입 [`first`, `last`)으로 제어 되는 시퀀스에서 `right` 가리키는 제어 된 시퀀스의 요소 앞 `where`합니다. 또한 `right`로 제어되는 시퀀스에서 원래 하위 범위를 제거합니다. (If `right` `==` `this`, 범위 [`first`, `last`)로 가리키는 요소를 포함 하지 않아야 `where`.) Splice 다른 파티션으로 한 목록에서 0 개 이상의 요소는 하위 시퀀스를 사용 합니다.  
  
## <a name="example"></a>예제  
  
```  
// cliext_list_splice.cpp   
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
  
// splice to a new list   
    cliext::list<wchar_t> c2;   
    c2.splice(c2.begin(), c1);   
    System::Console::WriteLine("c1.size() = {0}", c1.size());   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// return one element   
    c1.splice(c1.end(), c2, c2.begin());   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// return remaining elements   
    c1.splice(c1.begin(), c2, c2.begin(), c2.end());   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine("c2.size() = {0}", c2.size());   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
c1.size() = 0  
 a b c  
 a  
 b c  
 b c a  
c2.size() = 0  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/목록 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [list (STL/CLR)](../dotnet/list-stl-clr.md)   
 [list:: assign (STL/CLR)](../dotnet/list-assign-stl-clr.md)   
 [list:: insert (STL/CLR)](../dotnet/list-insert-stl-clr.md)   
 [list::merge(STL/CLR)](../dotnet/list-merge-stl-clr.md)