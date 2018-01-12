---
title: 'range_adapter:: range_adapter (STL/CLR) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::range_adapter::range_adapter
dev_langs: C++
helpviewer_keywords: range_adapter member [STL/CLR]
ms.assetid: b16af13f-3358-4e82-927d-d0d4986bcb18
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 3a8b93b6a02a2ad0db7282f7e5e8e3159dd23add
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="rangeadapterrangeadapter-stlclr"></a>range_adapter::range_adapter(STL/CLR)
어댑터 개체를 생성 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
range_adapter();  
range_adapter(range_adapter<Iter>% right);  
range_adapter(range_adapter<Iter>^ right);  
range_adapter(Iter first, Iter last);  
```  
  
#### <a name="parameters"></a>매개 변수  
 첫 번째  
 래핑할 첫 번째 반복기입니다.  
  
 last  
 줄 바꿈 두 번째 반복기입니다.  
  
 오른쪽  
 복사할 개체입니다.  
  
## <a name="remarks"></a>설명  
 생성자:  
  
 `range_adapter();`  
  
 저장 된 반복기 쌍을 생성할 기본 반복기를 초기화합니다.  
  
 생성자:  
  
 `range_adapter(range_adapter<Iter>% right);`  
  
 에 저장 된 쌍을 복사 하 여 저장 된 반복기 쌍을 초기화 합니다. `right`합니다.  
  
 생성자:  
  
 `range_adapter(range_adapter<Iter>^ right);`  
  
 에 저장 된 쌍을 복사 하 여 저장 된 반복기 쌍을 초기화 합니다. `*right`합니다.  
  
 생성자:  
  
 `range_adapter(Iter^ first, last);`  
  
 저장 된 반복기 쌍으로 초기화 `first` 및 `last`합니다.  
  
## <a name="example"></a>예  
  
```  
// cliext_range_adapter_construct.cpp   
// compile with: /clr   
#include <cliext/adapter>   
#include <cliext/deque>   
  
typedef cliext::deque<wchar_t> Mycont;   
typedef cliext::range_adapter<Mycont::iterator> Myrange;   
int main()   
    {   
    cliext::deque<wchar_t> d1;   
    d1.push_back(L'a');   
    d1.push_back(L'b');   
    d1.push_back(L'c');   
  
// construct an empty adapter   
    Myrange c1;   
  
// construct with an iterator pair   
    Myrange c2(d1.begin(), d1.end());   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another adapter   
    Myrange c3(c2);   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying an adapter handle   
    Myrange c4(%c3);   
    for each (wchar_t elem in c4)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    return (0);   
    }  
  
```  
  
```Output  
a b c  
a b c  
a b c  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/어댑터 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [range_adapter (STL/CLR)](../dotnet/range-adapter-stl-clr.md)   
 [range_adapter::operator=(STL/CLR)](../dotnet/range-adapter-operator-assign-stl-clr.md)