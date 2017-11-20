---
title: 'stack:: get_container (STL/CLR) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::stack::get_container
dev_langs: C++
helpviewer_keywords: get_container member [STL/CLR]
ms.assetid: ba6fc541-fc18-4d1c-8e3f-6baaed427cbb
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5f6b0d984559c82fb283bfb563c3309936ede9b8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="stackgetcontainer-stlclr"></a>stack::get_container(STL/CLR)
기본 컨테이너에 액세스합니다.  
  
## <a name="syntax"></a>구문  
  
```  
container_type^ get_container();  
```  
  
## <a name="remarks"></a>설명  
 멤버 함수는 기본 컨테이너에 대 한 핸들을 반환합니다. 컨테이너 래퍼가 설정 된 제한을 사용 하지 않으려면 사용 합니다.  
  
## <a name="example"></a>예제  
  
```  
// cliext_stack_get_container.cpp   
// compile with: /clr   
#include <cliext/stack>   
  
typedef cliext::stack<wchar_t> Mystack;   
int main()   
    {   
    Mystack c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display contents " a b c" using container_type   
    Mystack::container_type wc1 = c1.get_container();   
    for each (wchar_t elem in wc1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/스택 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [stack (STL/CLR)](../dotnet/stack-stl-clr.md)   
 [stack::container_type(STL/CLR)](../dotnet/stack-container-type-stl-clr.md)