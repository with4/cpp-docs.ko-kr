---
title: 'multimap:: key_comp (STL/CLR) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::multimap::key_comp
dev_langs:
- C++
helpviewer_keywords:
- key_comp member [STL/CLR]
ms.assetid: 05250549-d589-4e1d-8ae9-321ff4ad384b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: fc39cc3202c25fd0993831b46cc2961ef19f1826
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="multimapkeycomp-stlclr"></a>multimap::key_comp(STL/CLR)
두 키에 대 한 순서 지정 대리자를 복사합니다.  
  
## <a name="syntax"></a>구문  
  
```  
key_compare^key_comp();  
```  
  
## <a name="remarks"></a>설명  
 멤버 함수는 제어 되는 시퀀스를 정렬 하는 데 사용 되는 정렬 대리자를 반환 합니다. 두 키를 비교할를 사용 합니다.  
  
## <a name="example"></a>예  
  
```  
// cliext_multimap_key_comp.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::multimap<wchar_t, int> Mymultimap;   
int main()   
    {   
    Mymultimap c1;   
    Mymultimap::key_compare^ kcomp = c1.key_comp();   
  
    System::Console::WriteLine("compare(L'a', L'a') = {0}",   
        kcomp(L'a', L'a'));   
    System::Console::WriteLine("compare(L'a', L'b') = {0}",   
        kcomp(L'a', L'b'));   
    System::Console::WriteLine("compare(L'b', L'a') = {0}",   
        kcomp(L'b', L'a'));   
    System::Console::WriteLine();   
  
// test a different ordering rule   
    Mymultimap c2 = cliext::greater<wchar_t>();   
    kcomp = c2.key_comp();   
  
    System::Console::WriteLine("compare(L'a', L'a') = {0}",   
        kcomp(L'a', L'a'));   
    System::Console::WriteLine("compare(L'a', L'b') = {0}",   
        kcomp(L'a', L'b'));   
    System::Console::WriteLine("compare(L'b', L'a') = {0}",   
        kcomp(L'b', L'a'));   
    return (0);   
    }  
  
```  
  
```Output  
compare(L'a', L'a') = False  
compare(L'a', L'b') = True  
compare(L'b', L'a') = False  
  
compare(L'a', L'a') = False  
compare(L'a', L'b') = False  
compare(L'b', L'a') = True  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/매핑 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [multimap (STL/CLR)](../dotnet/multimap-stl-clr.md)   
 [multimap:: key_compare (STL/CLR)](../dotnet/multimap-key-compare-stl-clr.md)   
 [multimap::key_type(STL/CLR)](../dotnet/multimap-key-type-stl-clr.md)