---
title: 'list:: merge (STL/CLR) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::list::merge
dev_langs:
- C++
helpviewer_keywords:
- merge member [STL/CLR]
ms.assetid: f8e93cd3-bd08-4086-859b-08a2899cc9a6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: ff5ba18dea3b33d1cf3a50dedfc5e90055e69c3e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33133404"
---
# <a name="listmerge-stlclr"></a>list::병합(STL/CLR)
제어 된 시퀀스를 정렬 된 두 개의 병합 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
void merge(list<Value>% right);  
template<typename Pred2>  
    void merge(list<Value>% right, Pred2 pred);  
```  
  
#### <a name="parameters"></a>매개 변수  
 pred  
 요소 쌍에 대 한 비교자입니다.  
  
 오른쪽  
 컨테이너에서의 merge입니다.  
  
## <a name="remarks"></a>설명  
 첫 번째 멤버 함수에 의해 제어 되는 시퀀스에서 요소를 모두 제거 `right` 제어 되는 시퀀스에 삽입 합니다. 두 시퀀스에서 이전에 정렬 되어야 합니다 `operator<` -시퀀스를 진행 하면서 요소 값에서 감소 하지 해야 합니다. 결과 시퀀스로 정렬 `operator<`합니다. 이 멤버 함수를 사용 하 여 값에도 증가 하는 시퀀스에 값이 증가 하는 두 개의 시퀀스를 병합 합니다.  
  
 두 번째 멤버 함수는 동일 하 게 동작 첫 번째 시퀀스의 기준으로 정렬 된 한다는 점을 제외 하면 `pred`  --  `pred(X, Y)` 모든 요소에 대해 false 이어야 합니다 `X` 요소 다음에 오는 `Y` 시퀀스에서 합니다. 병합 조건자 함수 또는 사용자가 지정한 대리자에 의해 정렬 된 두 개의 시퀀스를 사용 합니다.  
  
 모두 안정적인 병합을 수행 하는 함수에 결과 제어 된 시퀀스에서 원래 제어 된 시퀀스 중 하나에 있는 요소의 없는 쌍 속도가 반대로 바뀝니다. 또한 경우 요소의 쌍 `X` 및 `Y` 순서 지정이 동일할-결과 제어 되는 시퀀스에 `!(X < Y) && !(X < Y)` -제어 되는 원래 시퀀스에서 요소 에의해제어되는시퀀스에서요소앞에표시되`right`.  
  
## <a name="example"></a>예제  
  
```  
// cliext_list_merge.cpp   
// compile with: /clr   
#include <cliext/list>   
  
typedef cliext::list<wchar_t> Mylist;   
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'c');   
    c1.push_back(L'e');   
  
// display initial contents " a c e"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    cliext::list<wchar_t> c2;   
    c2.push_back(L'b');   
    c2.push_back(L'd');   
    c2.push_back(L'f');   
  
// display initial contents " b d f"   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// merge and display   
    cliext::list<wchar_t> c3(c1);   
    c3.merge(c2);   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine("c2.size() = {0}", c2.size());   
  
// sort descending, merge descending, and redisplay   
    c1.sort(cliext::greater<wchar_t>());   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    c3.sort(cliext::greater<wchar_t>());   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    c3.merge(c1, cliext::greater<wchar_t>());   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine("c1.size() = {0}", c1.size());   
    return (0);   
    }  
  
```  
  
```Output  
 a c e  
 b d f  
 a b c d e f  
c2.size() = 0  
 e c a  
 f e d c b a  
 f e e d c c b a a  
c1.size() = 0  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/목록 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [list (STL/CLR)](../dotnet/list-stl-clr.md)   
 [list:: sort (STL/CLR)](../dotnet/list-sort-stl-clr.md)   
 [list::splice(STL/CLR)](../dotnet/list-splice-stl-clr.md)