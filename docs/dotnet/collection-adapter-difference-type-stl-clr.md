---
title: 'collection_adapter:: difference_type (STL/CLR) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::collection_adapter::difference_type
dev_langs:
- C++
helpviewer_keywords:
- difference_type member [STL/CLR]
ms.assetid: ef263e3f-f932-4d64-9d27-429c7b8ba279
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: e8c022270eaf1d58c075a4b74a74a0c64cc4aea6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33104219"
---
# <a name="collectionadapterdifferencetype-stlclr"></a>collection_adapter::difference_type(STL/CLR)
두 요소 사이의 부호가 있는 거리의 형식입니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef int difference_type;  
```  
  
## <a name="remarks"></a>설명  
 형식은 부호 있는 요소 수를 설명 합니다.  
  
## <a name="example"></a>예제  
  
```  
// cliext_collection_adapter_difference_type.cpp   
// compile with: /clr   
#include <cliext/adapter>   
#include <cliext/deque>   
  
typedef cliext::collection_adapter<   
    System::Collections::ICollection> Mycoll;   
int main()   
    {   
    cliext::deque<wchar_t> d1;   
    d1.push_back(L'a');   
    d1.push_back(L'b');   
    d1.push_back(L'c');   
    Mycoll c1(%d1);   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// compute positive difference   
    Mycoll::difference_type diff = 0;   
    Mycoll::iterator it = c1.begin();   
    for (; it != c1.end(); ++it)   
        ++diff;   
    System::Console::WriteLine("end()-begin() = {0}", diff);   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
end()-begin() = 3  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/어댑터 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [collection_adapter (STL/CLR)](../dotnet/collection-adapter-stl-clr.md)   
 [collection_adapter::size_type(STL/CLR)](../dotnet/collection-adapter-size-type-stl-clr.md)