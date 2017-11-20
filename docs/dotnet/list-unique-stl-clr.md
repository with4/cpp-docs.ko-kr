---
title: 'list:: unique (STL/CLR) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::list::unique
dev_langs: C++
helpviewer_keywords: unique member [STL/CLR]
ms.assetid: c3a29e4e-0ec1-4472-b050-7a9511037132
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ca78fcc1de8b579a647dd9080dc64db0fde54e9b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="listunique-stlclr"></a>list::unique(STL/CLR)
지정된 테스트를 통과하는 인접 요소를 제거합니다.  
  
## <a name="syntax"></a>구문  
  
```  
void unique();  
template<typename Pred2>  
    void unique(Pred2 pred);  
```  
  
#### <a name="parameters"></a>매개 변수  
 pred  
 요소 쌍에 대 한 비교자입니다.  
  
## <a name="remarks"></a>설명  
 첫 번째 멤버 함수는 제어 된 시퀀스 (지우기로 적용)에서 제거 하는 경우를 비교 하는 모든 요소가 이전 요소-같음 요소 `X` 요소 앞에 오는 `Y` 및 `X == Y`, 멤버 함수를 제거 `Y`합니다. 사용할 있습니다 인접 요소의 모든 하위 시퀀스의 복사본을 하나만 남기고 모두 제거 하려면 해당 비교 같음. 되는 경우 제어 되는 시퀀스 정렬 되는 경우 등으로 호출 하 여 [list:: sort (STL/CLR)](../dotnet/list-sort-stl-clr.md)`()`, 멤버 함수는 고유 값이 있는 요소를 둡니다. (그래서 이러한 이름을 갖습니다.)  
  
 두 번째 멤버 함수는 동일 하 게 동작 첫 번째, 각 요소를 제거 한다는 점을 제외 하면 `Y` 요소는 다음에 오는 `X` 입니다 `pred(X, Y)`합니다. 조건자 함수 또는 사용자가 지정한 대리자를 충족 하는 인접 요소의 모든 하위 시퀀스의 복사본을 하나만 남기고 모두 제거 하려면 사용 합니다. 되는 경우 제어 되는 시퀀스 정렬 되는 경우 등으로 호출 하 여 `sort(pred)`, 멤버 함수는 다른 요소와 순서 지정이 동일할 갖지 않는 요소만를 둡니다.  
  
## <a name="example"></a>예제  
  
```  
// cliext_list_unique.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// display contents after unique   
    cliext::list<wchar_t> c2(c1);   
    c2.unique();   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// display contents after unique(not_equal_to)   
    c2 = c1;   
    c2.unique(cliext::not_equal_to<wchar_t>());   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a a b c  
a b c  
a a  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/목록 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [list (STL/CLR)](../dotnet/list-stl-clr.md)   
 [list:: remove (STL/CLR)](../dotnet/list-remove-stl-clr.md)   
 [list:: remove_if (STL/CLR)](../dotnet/list-remove-if-stl-clr.md)   
 [list::sort(STL/CLR)](../dotnet/list-sort-stl-clr.md)