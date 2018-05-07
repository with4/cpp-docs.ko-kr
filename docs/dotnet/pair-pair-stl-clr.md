---
title: 'pair:: pair (STL/CLR) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::pair::pair
dev_langs:
- C++
helpviewer_keywords:
- pair member [STL/CLR]
ms.assetid: 188035f3-bd37-4b46-96dd-5ceb9a16df79
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 62e16307a96f1f6b672013c2e3c37946942736b8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="pairpair-stlclr"></a>pair::pair(STL/CLR)
쌍 개체를 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```  
pair();  
pair(pair<Coll>% right);  
pair(pair<Coll>^ right);  
pair(Value1 val1, Value2 val2);  
```  
  
#### <a name="parameters"></a>매개 변수  
 오른쪽  
 저장할 쌍입니다.  
  
 val1  
 첫 번째 저장할 값입니다.  
  
 v a l 2  
 두 번째 저장할 값입니다.  
  
## <a name="remarks"></a>설명  
 생성자:  
  
 `pair();`  
  
 기본 생성 값으로 저장된 쌍을 초기화합니다.  
  
 생성자:  
  
 `pair(pair<Value1, Value2>% right);`  
  
 저장 된 쌍을 이루는 초기화 `right.` [pair:: first (STL/CLR)](../dotnet/pair-first-stl-clr.md) 및 `right.` [pair:: second (STL/CLR)](../dotnet/pair-second-stl-clr.md)합니다.  
  
 `pair(pair<Value1, Value2>^ right);`  
  
 저장 된 쌍을 이루는 초기화 `right->` [pair:: first (STL/CLR)](../dotnet/pair-first-stl-clr.md) 및 `right>` [pair:: second (STL/CLR)](../dotnet/pair-second-stl-clr.md)합니다.  
  
 생성자:  
  
 `pair(Value1 val1, Value2 val2);`  
  
 와 저장된 쌍으로 초기화 `val1` 및 `val2`합니다.  
  
## <a name="example"></a>예제  
  
```  
// cliext_pair_construct.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
// construct an empty container   
    cliext::pair<wchar_t, int> c1;   
    System::Console::WriteLine("[{0}, {1}]",   
        c1.first == L'\0' ? "\\0" : "??", c1.second);   
  
// construct with a pair of values   
    cliext::pair<wchar_t, int> c2(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);   
  
// construct by copying another pair   
    cliext::pair<wchar_t, int> c3(c2);   
    System::Console::WriteLine("[{0}, {1}]", c3.first, c3.second);   
  
// construct by copying a pair handle   
    cliext::pair<wchar_t, int> c4(%c3);   
    System::Console::WriteLine("[{0}, {1}]", c4.first, c4.second);   
  
    return (0);   
    }  
  
```  
  
```Output  
[\0, 0]  
[x, 3]  
[x, 3]  
[x, 3]  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/유틸리티 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [pair(STL/CLR)](../dotnet/pair-stl-clr.md)