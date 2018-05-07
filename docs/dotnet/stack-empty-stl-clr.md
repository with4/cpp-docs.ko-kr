---
title: 'stack:: empty (STL/CLR) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::stack::empty
dev_langs:
- C++
helpviewer_keywords:
- empty member [STL/CLR]
ms.assetid: 30bb4ec6-e7a1-4137-99ba-0e0ebdf31baf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: e6af0d89dead2a79a853a51943ffdf2778ee9c7d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="stackempty-stlclr"></a>stack::empty(STL/CLR)
요소가 있는지 여부를 테스트합니다.  
  
## <a name="syntax"></a>구문  
  
```  
bool empty();  
```  
  
## <a name="remarks"></a>설명  
 멤버 함수는 빈 제어되는 시퀀스에 대해 true를 반환합니다. 동일 [stack:: size (STL/CLR)](../dotnet/stack-size-stl-clr.md)`() == 0`합니다. 스택이 비어 있는지 여부를 테스트 사용 합니다.  
  
## <a name="example"></a>예제  
  
```  
// cliext_stack_empty.cpp   
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
    System::Console::WriteLine("size() = {0}", c1.size());   
    System::Console::WriteLine("empty() = {0}", c1.empty());   
  
// clear the container and reinspect   
    c1.pop();   
    c1.pop();   
    c1.pop();   
    System::Console::WriteLine("size() = {0}", c1.size());   
    System::Console::WriteLine("empty() = {0}", c1.empty());   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
size() = 3  
empty() = False  
size() = 0  
empty() = True  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/스택 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [stack (STL/CLR)](../dotnet/stack-stl-clr.md)   
 [stack::size(STL/CLR)](../dotnet/stack-size-stl-clr.md)