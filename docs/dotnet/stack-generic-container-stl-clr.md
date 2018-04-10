---
title: 'stack:: generic_container (STL/CLR) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- cliext::stack::generic_container
dev_langs:
- C++
helpviewer_keywords:
- generic_container member [STL/CLR]
ms.assetid: 00f106c4-2a02-41cd-80de-f413c9355c74
caps.latest.revision: 14
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: bf2611401b60341bedf15fd38f85e1701482c9d5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="stackgenericcontainer-stlclr"></a>stack::generic_container(STL/CLR)
컨테이너 어댑터에 대 한 제네릭 인터페이스의 형식입니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef Microsoft::VisualC::StlClr::IStack<Value>  
    generic_container;  
```  
  
## <a name="remarks"></a>설명  
 이 형식은이 템플릿 컨테이너 어댑터 클래스에 대 한 제네릭 인터페이스를 설명 합니다.  
  
## <a name="example"></a>예  
  
```  
// cliext_stack_generic_container.cpp   
// compile with: /clr   
#include <cliext/stack>   
  
typedef cliext::stack<wchar_t> Mystack;   
int main()   
    {   
    Mystack c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// get interface to container   
    Mystack::generic_container^ gc1 = %c1;   
    for each (wchar_t elem in gc1->get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// modify generic and display original   
    gc1->push(L'd');   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// modify original and display generic   
    c1.push(L'e');   
    for each (wchar_t elem in gc1->get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
a b c  
a b c d  
a b c d e  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/스택 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualC.StlClr.IStack%602>   
 [stack (STL/CLR)](../dotnet/stack-stl-clr.md)   
 [stack::generic_value(STL/CLR)](../dotnet/stack-generic-value-stl-clr.md)