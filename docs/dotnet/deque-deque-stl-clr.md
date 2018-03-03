---
title: 'deque:: deque (STL/CLR) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::deque::deque
dev_langs:
- C++
helpviewer_keywords:
- deque member [STL/CLR]
ms.assetid: e5bc9511-619e-469c-b50a-e06858e7fce7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: b077e4c92d9307b8ff99126c824d0a902ce1ff83
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="dequedeque-stlclr"></a>deque::deque(STL/CLR)
컨테이너 개체를 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```  
deque();  
deque(deque<Value>% right);  
deque(deque<Value>^ right);  
explicit deque(size_type count);  
deque(size_type count, value_type val);  
template<typename InIt>  
    deque(InIt first, InIt last);  
deque(System::Collections::Generic::IEnumerable<Value>^ right);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `count`  
 삽입할 요소의 수입니다.  
  
 `first`  
 삽입할 범위의의 시작입니다.  
  
 `last`  
 삽입할 범위의 끝입니다.  
  
 `right`  
 삽입할 개체 또는 범위입니다.  
  
 `val`  
 삽입할 요소의 값입니다.  
  
## <a name="remarks"></a>설명  
 생성자:  
  
 `deque();`  
  
 요소가 없는 제어 되는 시퀀스를 초기화합니다. 초기는 빈 제어 시퀀스를 지정 하려면 사용 합니다.  
  
 생성자:  
  
 `deque(deque<Value>% right);`  
  
 순서와 제어 된 시퀀스를 초기화 합니다. [`right.begin()`, `right.end()`). Deque 개체에 의해 제어 되는 시퀀스의 복사본 인는 초기 제어 시퀀스를 지정 하려면 사용할 `right`합니다. 반복기에 대 한 자세한 내용은 참조 하십시오. [deque:: begin (STL/CLR)](../dotnet/deque-begin-stl-clr.md) 및 [deque:: end (STL/CLR)](../dotnet/deque-end-stl-clr.md)합니다.  
  
 생성자:  
  
 `deque(deque<Value>^ right);`  
  
 순서와 제어 된 시퀀스를 초기화 합니다. [`right->begin()`, `right->end()`). 핸들은 e q u e 개체에 의해 제어 되는 시퀀스의 복사본 인는 초기 제어 시퀀스를 지정 하려면 사용할 `right`합니다.  
  
 생성자:  
  
 `explicit deque(size_type count);`  
  
 이 있는 제어 된 시퀀스를 초기화 `count` 각 요소 값을 가진 `value_type()`합니다. 있습니다을 채우는 데 사용할 컨테이너 요소와 모든 기본 값이 포함 됩니다.  
  
 생성자:  
  
 `deque(size_type count, value_type val);`  
  
 이 있는 제어 된 시퀀스를 초기화 `count` 각 요소 값을 가진 `val`합니다. 하면을 채우는 데 사용할 컨테이너 요소와 동일한 값이 모두 포함 합니다.  
  
 생성자:  
  
 `template<typename InIt>`  
  
 `deque(InIt first, InIt last);`  
  
 순서와 제어 된 시퀀스를 초기화 합니다. [`first`, `last`). 제어 되는 시퀀스의 사본을 다른 시퀀스를 사용 합니다.  
  
 생성자:  
  
 `deque(System::Collections::Generic::IEnumerable<Value>^ right);`  
  
 열거자에 지정 된 시퀀스와 제어 된 시퀀스를 초기화 `right`합니다. 제어 되는 시퀀스의 사본을 열거자에서 설명 하는 다른 시퀀스를 사용 합니다.  
  
## <a name="example"></a>예  
  
```cpp  
// cliext_deque_construct.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
// construct an empty container   
    cliext::deque<wchar_t> c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// construct with a repetition of default values   
    cliext::deque<wchar_t> c2(3);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", (int)elem);   
    System::Console::WriteLine();   
  
// construct with a repetition of values   
    cliext::deque<wchar_t> c3(6, L'x');   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range   
    cliext::deque<wchar_t>::iterator it = c3.end();   
    cliext::deque<wchar_t> c4(c3.begin(), --it);   
    for each (wchar_t elem in c4)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an enumeration   
    cliext::deque<wchar_t> c5(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3);   
    for each (wchar_t elem in c5)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    cliext::deque<wchar_t> c7(c3);   
    for each (wchar_t elem in c7)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying a container handle   
    cliext::deque<wchar_t> c8(%c3);   
    for each (wchar_t elem in c8)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    return (0);   
    }  
  
```  
  
```Output  
size() = 0  
 0 0 0  
 x x x x x x  
 x x x x x  
 x x x x x x  
 x x x x x x  
 x x x x x x  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/q u e >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [deque (STL/CLR)](../dotnet/deque-stl-clr.md)   
 [deque:: assign (STL/CLR)](../dotnet/deque-assign-stl-clr.md)   
 [deque:: generic_container (STL/CLR)](../dotnet/deque-generic-container-stl-clr.md)   
 [operator= (deque)(STL/CLR)](../dotnet/operator-assign-deque-stl-clr.md)