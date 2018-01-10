---
title: 'vector:: front_item (STL/CLR) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::vector::front_item
dev_langs: C++
helpviewer_keywords: front_item member [STL/CLR]
ms.assetid: 7db87868-3e54-4c67-a06b-01bcfff3128d
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: fa6931e05c62674f094bb1e3870a0b8b627f6a0a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="vectorfrontitem-stlclr"></a>vector::front_item(STL/CLR)
첫 번째 요소에 액세스합니다.  
  
## <a name="syntax"></a>구문  
  
```  
property value_type front_item;  
```  
  
## <a name="remarks"></a>설명  
 비어 있는 제어 된 시퀀스의 첫 번째 요소를 액세스 하는 속성입니다. 읽기 또는 존재 하는 것을 알고 있는 경우 첫 번째 요소를 쓰기를 사용 합니다.  
  
## <a name="example"></a>예  
  
```  
// cliext_vector_front_item.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect first item   
    System::Console::WriteLine("front_item = {0}", c1.front_item);   
  
// alter first item and reinspect   
    c1.front_item = L'x';   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
front_item = a  
 x b c  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/벡터 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [vector (STL/CLR)](../dotnet/vector-stl-clr.md)   
 [vector:: back (STL/CLR)](../dotnet/vector-back-stl-clr.md)   
 [vector:: back_item (STL/CLR)](../dotnet/vector-back-item-stl-clr.md)   
 [vector::front(STL/CLR)](../dotnet/vector-front-stl-clr.md)