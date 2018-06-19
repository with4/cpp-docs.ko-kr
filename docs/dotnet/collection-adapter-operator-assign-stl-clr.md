---
title: 'collection_adapter:: operator = (STL/CLR) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::collection_adapter::operator=
dev_langs:
- C++
helpviewer_keywords:
- operator= member [STL/CLR]
ms.assetid: 45365a33-3b56-4cb7-962f-81c20d8901d3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 5c0374293def9751655c38c9a69650ff11c68cb5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33106507"
---
# <a name="collectionadapteroperator-stlclr"></a>collection_adapter::operator=(STL/CLR)
저장된 BCL 핸들을 대체합니다.  
  
## <a name="syntax"></a>구문  
  
```  
collection_adapter<Coll>% operator=(collection_adapter<Coll>% right);  
```  
  
#### <a name="parameters"></a>매개 변수  
 오른쪽  
 복사할 어댑터입니다.  
  
## <a name="remarks"></a>설명  
 멤버 연산자 복사본 `right` 개체에 반환 `*this`합니다. 에 저장 된 BCL 핸들의 복사본이 저장된 BCL 핸들 바꿉니다 사용 `right`합니다.  
  
## <a name="example"></a>예제  
  
```  
// cliext_collection_adapter_operator_as.cpp   
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
  
// assign to a new container   
    Mycoll c2;   
    c2 = c1;   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
a b c  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/어댑터 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [collection_adapter(STL/CLR)](../dotnet/collection-adapter-stl-clr.md)