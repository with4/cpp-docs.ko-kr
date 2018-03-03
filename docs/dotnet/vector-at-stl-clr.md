---
title: 'vector:: at (STL/CLR) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::vector::at
dev_langs:
- C++
helpviewer_keywords:
- at member [STL/CLR]
ms.assetid: 9af9f829-48b8-4906-ba4a-b43454acb2c7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 7f8747242f757855b58a72a4604e84200df02a6c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="vectorat-stlclr"></a>vector::at(STL/CLR)
지정된 위치에 있는 요소에 액세스합니다.  
  
## <a name="syntax"></a>구문  
  
```  
reference at(size_type pos);  
```  
  
#### <a name="parameters"></a>매개 변수  
 위치  
 액세스할 요소의 위치입니다.  
  
## <a name="remarks"></a>설명  
 멤버 함수는 위치에서 제어 된 시퀀스의 요소에 대 한 참조를 반환 `pos`합니다. 읽기 또는 쓰기 요소 위치를 알아야 합니다.  
  
## <a name="example"></a>예  
  
```  
// cliext_vector_at.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c" using at   
    for (int i = 0; i < c1.size(); ++i)   
        System::Console::Write(" {0}", c1.at(i));   
    System::Console::WriteLine();   
  
// change an entry and redisplay   
    c1.at(1) = L'x';   
    for (int i = 0; i < c1.size(); ++i)   
        System::Console::Write(" {0}", c1[i]);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
a x c  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/벡터 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [vector (STL/CLR)](../dotnet/vector-stl-clr.md)   
 [vector::operator(STL/CLR)](../dotnet/vector-operator-stl-clr.md)