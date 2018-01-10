---
title: 'list:: remove_if (STL/CLR) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::list::remove_if
dev_langs: C++
helpviewer_keywords: remove_if member [STL/CLR]
ms.assetid: cbc66192-751b-41c5-b557-d5d7bbc2a840
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 39cdd5fe6f7bf143b6e46b8fcde1a34f919be191
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="listremoveif-stlclr"></a>list::remove_if(STL/CLR)
지정 된 테스트를 통과 하는 요소를 제거 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
template<typename Pred1>  
    void remove_if(Pred1 pred);  
```  
  
#### <a name="parameters"></a>매개 변수  
 pred  
 제거할 요소에 대 한 테스트 합니다.  
  
## <a name="remarks"></a>설명  
 멤버 함수는 제어 된 시퀀스 (지우기로 적용)에서 제거 모든 요소가 `X` 를 `pred(X)` 그렇습니다. 함수 또는 대리자도 지정 하는 조건을 만족 하는 모든 요소를 제거 하려면 사용 합니다.  
  
## <a name="example"></a>예  
  
```  
// cliext_list_remove_if.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'b');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b b b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// fail to remove and redisplay   
    c1.remove_if(cliext::binder2nd<cliext::equal_to<wchar_t> >(   
        cliext::equal_to<wchar_t>(), L'd'));   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// remove and redisplay   
    c1.remove_if(cliext::binder2nd<cliext::not_equal_to<wchar_t> >(   
        cliext::not_equal_to<wchar_t>(), L'b'));   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b b b c  
a b b b c  
b b b  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/목록 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [list (STL/CLR)](../dotnet/list-stl-clr.md)   
 [list:: clear (STL/CLR)](../dotnet/list-clear-stl-clr.md)   
 [list:: erase (STL/CLR)](../dotnet/list-erase-stl-clr.md)   
 [list:: remove (STL/CLR)](../dotnet/list-remove-stl-clr.md)   
 [list::unique(STL/CLR)](../dotnet/list-unique-stl-clr.md)