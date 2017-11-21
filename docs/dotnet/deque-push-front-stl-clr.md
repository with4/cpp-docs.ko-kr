---
title: 'deque:: push_front (STL/CLR) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::deque::push_front
dev_langs: C++
helpviewer_keywords: push_front member [STL/CLR]
ms.assetid: a452c94e-abad-4e28-af41-c73ec805ec6f
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 110c1eb538c08b8bba891433e639a0f6559a6d1d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="dequepushfront-stlclr"></a>deque::push_front(STL/CLR)
새 첫 번째 요소를 추가 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
void push_front(value_type val);  
```  
  
## <a name="remarks"></a>설명  
 멤버 함수는 값을 가진 요소를 삽입 `val` 제어 된 시퀀스의 시작 부분에 있습니다. Deque에 다른 요소 앞에 사용 합니다.  
  
## <a name="example"></a>예제  
  
```  
// cliext_deque_push_front.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
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
 **헤더:** \<cliext/q u e >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [deque (STL/CLR)](../dotnet/deque-stl-clr.md)   
 [deque:: pop_back (STL/CLR)](../dotnet/deque-pop-back-stl-clr.md)   
 [deque:: pop_front (STL/CLR)](../dotnet/deque-pop-front-stl-clr.md)   
 [deque::push_back(STL/CLR)](../dotnet/deque-push-back-stl-clr.md)