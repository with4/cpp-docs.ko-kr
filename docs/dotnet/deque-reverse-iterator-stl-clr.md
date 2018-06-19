---
title: 'deque:: reverse_iterator (STL/CLR) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::deque::reverse_iterator
dev_langs:
- C++
helpviewer_keywords:
- reverse_iterator member [STL/CLR]
ms.assetid: 82bdfda7-496d-4f8a-8eb8-96bee83b5708
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 162ddfff2ff9f4834c445a45e282399a36b6665f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33107404"
---
# <a name="dequereverseiterator-stlclr"></a>deque::reverse_iterator(STL/CLR)
제어되는 시퀀스에 대한 반대 반복기의 형식입니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef T3 reverse_iterator;  
```  
  
## <a name="remarks"></a>설명  
 이 형식은 제어된 시퀀스에 대해 반대 반복기로 사용될 수 있는 지정되지 않은 `T3` 형식의 개체를 설명합니다.  
  
## <a name="example"></a>예제  
  
```  
// cliext_deque_reverse_iterator.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c" reversed   
    cliext::deque<wchar_t>::reverse_iterator rit = c1.rbegin();   
    for (; rit != c1.rend(); ++rit)   
        System::Console::Write(" {0}", *rit);   
    System::Console::WriteLine();   
  
// alter first element and redisplay   
    rit = c1.rbegin();   
    *rit = L'x';   
    for (; rit != c1.rend(); ++rit)   
        System::Console::Write(" {0}", *rit);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
c b a  
x b a  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/q u e >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [deque (STL/CLR)](../dotnet/deque-stl-clr.md)   
 [deque:: const_iterator (STL/CLR)](../dotnet/deque-const-iterator-stl-clr.md)   
 [deque:: const_reverse_iterator (STL/CLR)](../dotnet/deque-const-reverse-iterator-stl-clr.md)   
 [deque::iterator(STL/CLR)](../dotnet/deque-iterator-stl-clr.md)