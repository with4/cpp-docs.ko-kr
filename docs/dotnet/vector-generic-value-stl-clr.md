---
title: 'vector:: generic_value (STL/CLR) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::vector::generic_value
dev_langs: C++
helpviewer_keywords: generic_value member [STL/CLR]
ms.assetid: 01fdc5c5-27d3-4dc2-b242-cae2fd04a60d
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 09b20068b2c0900c3a75524a0fe118d05ee1c0ef
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="vectorgenericvalue-stlclr"></a>vector::generic_value(STL/CLR)
컨테이너에 대 한 제네릭 인터페이스와 함께 사용 하기 위해 요소의 형식입니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef GValue generic_value;  
```  
  
## <a name="remarks"></a>설명  
 이 형식은 형식의 개체를 설명 `GValue` 이 서식 파일 컨테이너 클래스에 대 한 제네릭 인터페이스와 함께 사용 하기 위해 저장 된 요소 값을 설명 하는 합니다.  
  
## <a name="example"></a>예  
  
```  
// cliext_vector_generic_value.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct a generic container   
    cliext::vector<wchar_t>::generic_container^ gc1 = %c1;   
    for each (wchar_t elem in gc1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// modify generic and display original   
    cliext::vector<wchar_t>::generic_iterator gcit = gc1->begin();   
    cliext::vector<wchar_t>::generic_value gcval = *gcit;   
    *++gcit = gcval;   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
a b c  
a a c  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/벡터 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [vector (STL/CLR)](../dotnet/vector-stl-clr.md)   
 [vector:: generic_container (STL/CLR)](../dotnet/vector-generic-container-stl-clr.md)   
 [vector:: generic_iterator (STL/CLR)](../dotnet/vector-generic-iterator-stl-clr.md)   
 [vector::generic_reverse_iterator(STL/CLR)](../dotnet/vector-generic-reverse-iterator-stl-clr.md)