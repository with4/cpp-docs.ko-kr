---
title: 'map:: difference_type (STL/CLR) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::map::difference_type
dev_langs: C++
helpviewer_keywords: difference_type member [STL/CLR]
ms.assetid: 22c80391-f97b-4ac4-9e2d-7f4caa2c5ac8
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b0b28b6fe57be020e6f602a562ffd6df52aa14a0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="mapdifferencetype-stlclr"></a>map::difference_type(STL/CLR)
두 요소 사이의 부호가 있는 거리의 형식입니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef int difference_type;  
```  
  
## <a name="remarks"></a>설명  
 형식은 음수 수 있는 요소 수를 설명 합니다.  
  
## <a name="example"></a>예제  
  
```  
// cliext_map_difference_type.cpp   
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
  
// compute positive difference   
    Mymap::difference_type diff = 0;   
    for (Mymap::iterator it = c1.begin(); it != c1.end(); ++it)   
        ++diff;   
    System::Console::WriteLine("end()-begin() = {0}", diff);   
  
// compute negative difference   
    diff = 0;   
    for (Mymap::iterator it = c1.end(); it != c1.begin(); --it)   
        --diff;   
    System::Console::WriteLine("begin()-end() = {0}", diff);   
    return (0);   
    }  
  
```  
  
```Output  
 [a 1] [b 2] [c 3]  
end()-begin() = 3  
begin()-end() = -3  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/매핑 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [map (STL/CLR)](../dotnet/map-stl-clr.md)   
 [map::size_type(STL/CLR)](../dotnet/map-size-type-stl-clr.md)