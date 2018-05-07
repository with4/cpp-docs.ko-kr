---
title: deque::operator(STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::deque::operator[]
dev_langs:
- C++
helpviewer_keywords:
- operatormember [] [STL/CLR]
ms.assetid: d7653bb5-db48-4637-a25c-e7303e5d28da
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: b7b07f9206e5794b3bcbe219b35cf4d90fd4d8bc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="dequeoperatorstlclr"></a>deque::operator(STL/CLR)
지정된 위치에 있는 요소에 액세스합니다.  
  
## <a name="syntax"></a>구문  
  
```  
reference operator[](size_type pos);  
```  
  
#### <a name="parameters"></a>매개 변수  
 위치  
 액세스할 요소의 위치입니다.  
  
## <a name="remarks"></a>설명  
 멤버 연산자는 referene 위치에 요소를 반환 `pos`합니다. 요소를 알면 해당 위치에 액세스 사용 합니다.  
  
## <a name="example"></a>예제  
  
```  
// cliext_deque_operator_sub.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c" using subscripting   
    for (int i = 0; i < c1.size(); ++i)   
        System::Console::Write(" {0}", c1[i]);   
    System::Console::WriteLine();   
  
// change an entry and redisplay   
    c1[1] = L'x';   
    for (int i = 0; i < c1.size(); ++i)   
        System::Console::Write(" {0}", c1[i]);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
a x c  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/q u e >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [deque (STL/CLR)](../dotnet/deque-stl-clr.md)   
 [deque::at(STL/CLR)](../dotnet/deque-at-stl-clr.md)