---
title: 'stack:: const_reference (STL/CLR) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::stack::const_reference
dev_langs:
- C++
helpviewer_keywords:
- const_reference member [STL/CLR]
ms.assetid: 36be8e21-f2b8-4c2e-a00e-276e73f0d802
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 8caebc39b9101d31618452cfc41841b7af9432bc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="stackconstreference-stlclr"></a>stack::const_reference(STL/CLR)
요소에 대한 상수 참조의 형식입니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef value_type% const_reference;  
```  
  
## <a name="remarks"></a>설명  
 이 형식은 요소에 대 한 상수 참조를 설명 합니다.  
  
## <a name="example"></a>예  
  
```  
// cliext_stack_const_reference.cpp   
// compile with: /clr   
#include <cliext/stack>   
  
typedef cliext::stack<wchar_t> Mystack;   
int main()   
    {   
    Mystack c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display reversed contents " c b a"   
    for (; !c1.empty(); c1.pop())   
        {   // get a const reference to an element   
        Mystack::const_reference cref = c1.top();   
        System::Console::Write(" {0}", cref);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
c b a  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/스택 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [stack (STL/CLR)](../dotnet/stack-stl-clr.md)   
 [stack:: reference (STL/CLR)](../dotnet/stack-reference-stl-clr.md)   
 [stack::value_type(STL/CLR)](../dotnet/stack-value-type-stl-clr.md)