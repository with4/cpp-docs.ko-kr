---
title: 'vector:: clear (STL/CLR) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::vector::clear
dev_langs:
- C++
helpviewer_keywords:
- clear member [STL/CLR]
ms.assetid: 4ed20ec8-3089-4c36-b68f-1b51c639041f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 63fa3ce9b045abaef1c789705c83734180ea7de8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="vectorclear-stlclr"></a>vector::clear(STL/CLR)
모든 요소를 제거합니다.  
  
## <a name="syntax"></a>구문  
  
```  
void clear();  
```  
  
## <a name="remarks"></a>설명  
 멤버 함수 시그니처 [vector:: erase (STL/CLR)](../dotnet/vector-erase-stl-clr.md) `(` [vector:: begin (STL/CLR)](../dotnet/vector-begin-stl-clr.md) `(),` [vector:: end (STL/CLR)](../dotnet/vector-end-stl-clr.md) `())`. 제어 되는 시퀀스 비어 있는지 확인 하려면 사용 합니다.  
  
## <a name="example"></a>예제  
  
```  
// cliext_vector_clear.cpp   
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
  
// clear the container and reinspect   
    c1.clear();   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// add elements and clear again   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
  
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    c1.clear();   
    System::Console::WriteLine("size() = {0}", c1.size());   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
size() = 0  
 a b  
size() = 0  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/벡터 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [vector (STL/CLR)](../dotnet/vector-stl-clr.md)   
 [vector::erase(STL/CLR)](../dotnet/vector-erase-stl-clr.md)