---
title: 'stack:: reference (STL/CLR) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::stack::reference
dev_langs: C++
helpviewer_keywords: reference member [STL/CLR]
ms.assetid: 05c8fb2c-215c-4b83-80f9-d4d354577c6a
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 543170c470b0cbaec10b16ecfc7fe4f2b289ee22
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="stackreference-stlclr"></a>stack::reference(STL/CLR)
요소에 대한 참조의 형식입니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef value_type% reference;  
```  
  
## <a name="remarks"></a>설명  
 이 형식은 요소에 대 한 참조를 설명 합니다.  
  
## <a name="example"></a>예  
  
```  
// cliext_stack_reference.cpp   
// compile with: /clr   
#include <cliext/stack>   
  
typedef cliext::stack<wchar_t> Mystack;   
int main()   
    {   
    Mystack c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// modify top of stack and redisplay   
    Mystack::reference ref = c1.top();   
    ref = L'x';   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
a b x  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/스택 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [stack (STL/CLR)](../dotnet/stack-stl-clr.md)   
 [stack:: const_reference (STL/CLR)](../dotnet/stack-const-reference-stl-clr.md)   
 [stack::value_type(STL/CLR)](../dotnet/stack-value-type-stl-clr.md)