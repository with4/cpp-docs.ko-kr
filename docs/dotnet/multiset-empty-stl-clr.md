---
title: 'multiset:: empty (STL/CLR) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::multiset::empty
dev_langs:
- C++
helpviewer_keywords:
- empty member [STL/CLR]
ms.assetid: 59ec9cc4-cc72-4082-9ab2-49b49980e681
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 1bce912c9b530c39a5c7121c60e6a9a8a80ae852
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="multisetempty-stlclr"></a>multiset::empty(STL/CLR)
요소가 있는지 여부를 테스트합니다.  
  
## <a name="syntax"></a>구문  
  
```  
bool empty();  
```  
  
## <a name="remarks"></a>설명  
 멤버 함수는 빈 제어되는 시퀀스에 대해 true를 반환합니다. 동일 [multiset:: size (STL/CLR)](../dotnet/multiset-size-stl-clr.md)`() == 0`합니다. Multiset이 비어 있는지 여부를 테스트 사용 합니다.  
  
## <a name="example"></a>예  
  
```  
// cliext_multiset_empty.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine("size() = {0}", c1.size());   
    System::Console::WriteLine("empty() = {0}", c1.empty());   
  
// clear the container and reinspect   
    c1.clear();   
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
 **헤더:** \<cliext/set >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [multiset (STL/CLR)](../dotnet/multiset-stl-clr.md)   
 [multiset::size(STL/CLR)](../dotnet/multiset-size-stl-clr.md)