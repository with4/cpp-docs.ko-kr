---
title: 'stack:: stack (STL/CLR) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::stack::stack
dev_langs:
- C++
helpviewer_keywords:
- stack member [STL/CLR]
ms.assetid: f1cfb3fe-4d22-41e5-906b-e8faa0bcde9b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: e1ed49049a04f41e5a82ba7d25a52ce19c9a4898
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="stackstack-stlclr"></a>stack::stack(STL/CLR)
컨테이너 어댑터 개체를 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```  
stack();  
stack(stack<Value, Container>% right);  
stack(stack<Value, Container>^ right);  
explicit stack(container_type% wrapped);  
```  
  
#### <a name="parameters"></a>매개 변수  
 오른쪽  
 복사할 개체입니다.  
  
 래핑  
 래핑된 컨테이너를 사용 합니다.  
  
## <a name="remarks"></a>설명  
 생성자:  
  
 `stack();`  
  
 빈 래핑된 컨테이너를 만듭니다. 초기는 빈 제어 시퀀스를 지정 하려면 사용 합니다.  
  
 생성자:  
  
 `stack(stack<Value, Container>% right);`  
  
 복사본 인 래핑된 컨테이너를 만들고 `right.get_container()`합니다. 스택 개체에 의해 제어 되는 시퀀스의 복사본 인는 초기 제어 시퀀스를 지정 하려면 사용할 `right`합니다.  
  
 생성자:  
  
 `stack(stack<Value, Container>^ right);`  
  
 복사본 인 래핑된 컨테이너를 만들고 `right->get_container()`합니다. 스택 개체에 의해 제어 되는 시퀀스의 복사본 인는 초기 제어 시퀀스를 지정 하려면 사용할 `*right`합니다.  
  
 생성자:  
  
 `explicit stack(container_type% wrapped);`  
  
 기존 컨테이너를 사용 하 여 `wrapped` 래핑된 컨테이너로 합니다. 기존 컨테이너에서 스택을 생성을 사용 합니다.  
  
## <a name="example"></a>예제  
  
```  
// cliext_stack_construct.cpp   
// compile with: /clr   
#include <cliext/stack>   
#include <cliext/vector>   
  
typedef cliext::stack<wchar_t> Mystack;   
typedef cliext::vector<wchar_t> Myvector;   
typedef cliext::stack<wchar_t, Myvector> Mystack_vec;   
int main()   
    {   
// construct an empty container   
    Mystack c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// construct from an underlying container   
    Myvector v2(5, L'x');   
    Mystack_vec c2(v2);       
    for each (wchar_t elem in c2.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    Mystack_vec c3(c2);   
    for each (wchar_t elem in c3.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container through handle   
    Mystack_vec c4(%c2);   
    for each (wchar_t elem in c4.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
size() = 0  
 x x x x x  
 x x x x x  
 x x x x x  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/스택 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [stack (STL/CLR)](../dotnet/stack-stl-clr.md)   
 [stack:: assign (STL/CLR)](../dotnet/stack-assign-stl-clr.md)   
 [stack:: generic_container (STL/CLR)](../dotnet/stack-generic-container-stl-clr.md)   
 [stack::operator=(STL/CLR)](../dotnet/stack-operator-assign-stl-clr.md)