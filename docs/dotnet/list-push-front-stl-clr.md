---
title: 'list:: push_front (STL/CLR) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::list::push_front
dev_langs: C++
helpviewer_keywords: push_front member [STL/CLR]
ms.assetid: 47525641-1139-44fc-ac62-bdc04876d9e0
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 28c2526b15e0c6049b1f279b76d48455bdc82ac6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="listpushfront-stlclr"></a>list::push_front(STL/CLR)
새 첫 번째 요소를 추가 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
void push_front(value_type val);  
```  
  
## <a name="remarks"></a>설명  
 멤버 함수는 값을 가진 요소를 삽입 `val` 제어 된 시퀀스의 시작 부분에 있습니다. 목록에 다른 요소 앞에 사용 합니다.  
  
## <a name="example"></a>예제  
  
```  
// cliext_list_push_front.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_front(L'a');   
    c1.push_front(L'b');   
    c1.push_front(L'c');   
  
// display contents " c b a"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
c b a  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/목록 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [list (STL/CLR)](../dotnet/list-stl-clr.md)   
 [list:: pop_back (STL/CLR)](../dotnet/list-pop-back-stl-clr.md)   
 [list:: pop_front (STL/CLR)](../dotnet/list-pop-front-stl-clr.md)   
 [list::push_back(STL/CLR)](../dotnet/list-push-back-stl-clr.md)