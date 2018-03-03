---
title: 'stack:: push (STL/CLR) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::stack::push
dev_langs:
- C++
helpviewer_keywords:
- push member [STL/CLR]
ms.assetid: 60e5b076-c80f-4af0-a018-62cda7e081db
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 0ce5d9faba3e9dfd7e92cf603f9f6cb9b5f46486
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="stackpush-stlclr"></a>stack::push(STL/CLR)
새 마지막 요소를 추가 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
void push(value_type val);  
```  
  
## <a name="remarks"></a>설명  
 멤버 함수는 값을 가진 요소를 삽입 `val` 제어 된 시퀀스의 끝입니다. 스택에 추가 하는 다른 요소를 사용 합니다.  
  
## <a name="example"></a>예  
  
```  
// cliext_stack_push.cpp   
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
 [stack::pop(STL/CLR)](../dotnet/stack-pop-stl-clr.md)