---
title: 'pair:: first (STL/CLR) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::pair::first
dev_langs: C++
helpviewer_keywords: first member [STL/CLR]
ms.assetid: 0dd2278f-adf9-46df-8ac8-7e8e1a2ef52e
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 33b6183dd78225081c77e5cad06ed707f6bf7abe
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="pairfirst-stlclr"></a>pair::first(STL/CLR)
첫 번째 래핑한 값입니다.  
  
## <a name="syntax"></a>구문  
  
```  
Value1 first;  
```  
  
## <a name="remarks"></a>설명  
 개체는 첫 번째 래핑된 값을 저장합니다.  
  
## <a name="example"></a>예  
  
```  
// cliext_pair_first.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
    cliext::pair<wchar_t, int> c1(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
  
    cliext::pair<wchar_t, int>::first_type first_val = c1.first;   
    cliext::pair<wchar_t, int>::second_type second_val = c1.second;   
    System::Console::WriteLine("[{0}, {1}]", first_val, second_val);   
    return (0);   
    }  
  
```  
  
```Output  
[x, 3]  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/유틸리티 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [pair (STL/CLR)](../dotnet/pair-stl-clr.md)   
 [pair:: first_type (STL/CLR)](../dotnet/pair-first-type-stl-clr.md)   
 [pair:: second (STL/CLR)](../dotnet/pair-second-stl-clr.md)   
 [pair::second_type(STL/CLR)](../dotnet/pair-second-type-stl-clr.md)