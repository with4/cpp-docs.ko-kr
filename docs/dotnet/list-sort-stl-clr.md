---
title: 'list:: sort (STL/CLR) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::list::sort
dev_langs: C++
helpviewer_keywords: sort member [STL/CLR]
ms.assetid: f811d5f4-a19e-4194-8765-1e68097c52f0
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 159391bc7d362c755c194f478692b2a271d779ed
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="listsort-stlclr"></a>list::sort(STL/CLR)
제어 된 시퀀스를 정렬 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
void sort();  
template<typename Pred2>  
    void sort(Pred2 pred);  
```  
  
#### <a name="parameters"></a>매개 변수  
 pred  
 요소 쌍에 대 한 비교자입니다.  
  
## <a name="remarks"></a>설명  
 첫 번째 멤버 함수 다시 제어 된 시퀀스의 요소 정렬로 정렬 됩니다 있는 `operator<` -시퀀스를 진행 하면서 값 요소 줄어들지 않습니다. 이 멤버 함수를 사용 하 여 오름차순으로 정렬 순서를 정렬 합니다.  
  
 두 번째 멤버 함수는 동일 하 게 동작 첫 번째 시퀀스는 기준으로 정렬 한다는 점을 제외 하면 `pred`  --  `pred(X, Y)` 모든 요소에 대해 false가 `X` 요소 다음에 오는 `Y` 결과 시퀀스에서 합니다. 조건자 함수 또는 대리자에 의해 지정 된 순서에 따라 시퀀스를 정렬 하려면 사용 합니다.  
  
 모두 안정적인 정렬 수행 하는 기능이-결과 제어 된 시퀀스에서 제어 되는 원래 시퀀스의 요소 쌍 없는 속도가 반대로 바뀝니다.  
  
## <a name="example"></a>예  
  
```  
// cliext_list_sort.cpp   
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
  
// sort descending and redisplay   
    c1.sort(cliext::greater<wchar_t>());   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// sort ascending and redisplay   
    c1.sort();   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
c b a  
a b c  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/목록 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [list (STL/CLR)](../dotnet/list-stl-clr.md)   
 [list:: merge (STL/CLR)](../dotnet/list-merge-stl-clr.md)   
 [list:: reverse (STL/CLR)](../dotnet/list-reverse-stl-clr.md)   
 [list:: splice (STL/CLR)](../dotnet/list-splice-stl-clr.md)   
 [list::unique(STL/CLR)](../dotnet/list-unique-stl-clr.md)