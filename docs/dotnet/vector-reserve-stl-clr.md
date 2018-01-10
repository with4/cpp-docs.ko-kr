---
title: 'vector:: reserve (STL/CLR) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::vector::reserve
dev_langs: C++
helpviewer_keywords: reserve member [STL/CLR]
ms.assetid: d1d5ede9-9628-4b55-95ec-f087a57205f2
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 2c8c5ac474cc2b94baedab64854fec3ca3e0a78a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="vectorreserve-stlclr"></a>vector::reserve(STL/CLR)
컨테이너에 대 한 최소 증가 용량을 보장합니다.  
  
## <a name="syntax"></a>구문  
  
```  
void reserve(size_type count);  
```  
  
#### <a name="parameters"></a>매개 변수  
 count  
 새 컨테이너의 최소 용량입니다.  
  
## <a name="remarks"></a>설명  
 멤버 함수를 사용 하면 `capacity()` 예측이 이상 반환 `count`합니다. 컨테이너 지정된 된 크기 성장 했으며 될 때까지 제어 되는 시퀀스에 대 한 저장소 할당 되지 필요 하도록 사용할 수 있습니다.  
  
## <a name="example"></a>예  
  
```  
// cliext_vector_reserve.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for (int i = 0; i < c1.size(); ++i)   
        System::Console::Write(" {0}", c1.at(i));   
    System::Console::WriteLine();   
  
// increase capacity   
    cliext::vector<wchar_t>::size_type cap = c1.capacity();   
    System::Console::WriteLine("capacity() = {0}, ok = {1}",   
        cap, c1.size() <= cap);   
    c1.reserve(cap + 5);   
    System::Console::WriteLine("capacity() = {0}, ok = {1}",   
        c1.capacity(), cap + 5 <= c1.capacity());   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
capacity() = 4, ok = True  
capacity() = 9, ok = True  
```  
  
## <a name="description"></a>설명  
 여기에 표시 된 너무 오래 모든 값에서 실제 용량을 다를 수 있습니다 참고 `ok` 보고 되지 않으면 true입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/벡터 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [vector (STL/CLR)](../dotnet/vector-stl-clr.md)   
 [vector:: capacity (STL/CLR)](../dotnet/vector-capacity-stl-clr.md)   
 [vector::resize(STL/CLR)](../dotnet/vector-resize-stl-clr.md)