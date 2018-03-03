---
title: make_pair (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::make_pair
dev_langs:
- C++
helpviewer_keywords:
- make_pair function [STL/CLR]
ms.assetid: 74733f2c-97b0-4d69-b431-5ab8f0de9e3e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 34f86aefd9a7bad7b3b1f03f98d3df8965020e48
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="makepair-stlclr"></a>make_pair(STL/CLR)
확인 된 `pair` 값의 쌍에서입니다.  
  
## <a name="syntax"></a>구문  
  
```  
template<typename Value1,  
    typename Value2>  
    pair<Value1, Value2> make_pair(Value1 first, Value2 second);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `Value1`  
 첫 번째 래핑된 값의 형식입니다.  
  
 `Value2`  
 두 번째 래핑된 값의 형식입니다.  
  
 `first`  
 첫 번째 래핑할 값입니다.  
  
 `second`  
 두 번째 래핑할 값입니다.  
  
## <a name="remarks"></a>설명  
 템플릿 함수가 `pair<Value1, Value2>(first, second)`을 반환합니다. 생성에 사용 된 `pair<Value1, Value2>` 한 쌍의 값에서 개체입니다.  
  
## <a name="example"></a>예  
  
```cpp  
// cliext_make_pair.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
    cliext::pair<wchar_t, int> c1(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
  
    c1 = cliext::make_pair(L'y', 4);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
    return (0);   
    }  
  
```  
  
```Output  
[x, 3]  
[y, 4]  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/유틸리티 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [range_adapter(STL/CLR)](../dotnet/range-adapter-stl-clr.md)