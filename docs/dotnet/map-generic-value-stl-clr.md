---
title: 'map:: generic_value (STL/CLR) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::map::generic_value
dev_langs:
- C++
helpviewer_keywords:
- generic_value member [STL/CLR]
ms.assetid: bd42ec86-fb9e-4c0d-8cae-7187a8742a94
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 319e4c890672d9725bfa6dfd2dbdd5cf9e0c025e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="mapgenericvalue-stlclr"></a>map::generic_value(STL/CLR)
컨테이너에 대 한 제네릭 인터페이스와 함께 사용 하기 위해 요소의 형식입니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef GValue generic_value;  
```  
  
## <a name="remarks"></a>설명  
 이 형식은 형식의 개체를 설명 `GValue` 이 서식 파일 컨테이너 클래스에 대 한 제네릭 인터페이스와 함께 사용 하기 위해 저장 된 요소 값을 설명 하는 합니다.  
  
## <a name="example"></a>예제  
  
```  
// cliext_map_generic_value.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::map<wchar_t, int> Mymap;   
int main()   
    {   
    Mymap c1;   
    c1.insert(Mymap::make_value(L'a', 1));   
    c1.insert(Mymap::make_value(L'b', 2));   
    c1.insert(Mymap::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Mymap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct a generic container   
    Mymap::generic_container^ gc1 = %c1;   
    for each (Mymap::value_type elem in gc1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// get an element and display it   
    Mymap::generic_iterator gcit = gc1->begin();   
    Mymap::generic_value gcval = *gcit;   
    System::Console::WriteLine(" [{0} {1}]", gcval->first, gcval->second);   
    return (0);   
    }  
  
```  
  
```Output  
[a 1] [b 2] [c 3]  
[a 1] [b 2] [c 3]  
[a 1]  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/매핑 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [map (STL/CLR)](../dotnet/map-stl-clr.md)   
 [map:: generic_container (STL/CLR)](../dotnet/map-generic-container-stl-clr.md)   
 [map:: generic_iterator (STL/CLR)](../dotnet/map-generic-iterator-stl-clr.md)   
 [map::generic_reverse_iterator(STL/CLR)](../dotnet/map-generic-reverse-iterator-stl-clr.md)