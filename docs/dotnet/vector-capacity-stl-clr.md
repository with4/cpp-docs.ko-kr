---
title: 'vector:: capacity (STL/CLR) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::vector::capacity
dev_langs:
- C++
helpviewer_keywords:
- capacity member [STL/CLR]
ms.assetid: f82d8da9-8b4d-4288-8d18-8e9ca5911d87
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 9a08766c6b23deb4e36ad8c83f9c1f3e2bc1df1f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="vectorcapacity-stlclr"></a>vector::capacity(STL/CLR)
컨테이너에 할당 된 저장소의 크기를 보고합니다.  
  
## <a name="syntax"></a>구문  
  
```  
size_type capacity();  
```  
  
## <a name="remarks"></a>설명  
 멤버 함수는 제어 된 시퀀스도 큰 값을 보유할 현재 할당 된 저장소 반환 [vector:: size (STL/CLR)](../dotnet/vector-size-stl-clr.md)`()`합니다. 제어 되는 시퀀스에 대 한 저장소를 다시 할당 해야 하기 전에 얼마나 많은 컨테이너 증가할 수를 확인 하려면 사용 합니다.  
  
## <a name="example"></a>예제  
  
```  
// cliext_vector_capacity.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for (int i = 0; i < c1.size(); ++i)   
        System::Console::Write(" {0}", c1.at(i));   
    System::Console::WriteLine();   
  
// increase capacity   
    cliext::vector<wchar_t>::size_type cap = c1.capacity();   
    System::Console::WriteLine("capacity() = {0}, ok = {1}",   
        cap, c1.size() <= cap);   
    c1.reserve(cap + 5);   
    System::Console::WriteLine("capacity() = {0}, ok = {1}",   
        c1.capacity(), cap + 5 <= c1.capacity());   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
capacity() = 4, ok = True  
capacity() = 9, ok = True  
```  
  
## <a name="description"></a>설명  
 여기에 표시 된 너무 오래 모든 값에서 실제 용량을 다를 수 있습니다 참고 `ok` 보고 되지 않으면 true입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/벡터 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [vector (STL/CLR)](../dotnet/vector-stl-clr.md)   
 [vector::reserve(STL/CLR)](../dotnet/vector-reserve-stl-clr.md)