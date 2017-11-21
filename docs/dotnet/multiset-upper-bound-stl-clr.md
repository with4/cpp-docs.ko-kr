---
title: 'multiset:: upper_bound (STL/CLR) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::multiset::upper_bound
dev_langs: C++
helpviewer_keywords: upper_bound member [STL/CLR]
ms.assetid: 4a5af99f-a2a1-45be-9b01-c0055d4d0e35
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 7bccfbd395b2a6dfb20cb7a87e8860f23a591907
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="multisetupperbound-stlclr"></a>multiset::upper_bound(STL/CLR)
지정된 된 키와 일치 하는 범위의 끝을 찾습니다.  
  
## <a name="syntax"></a>구문  
  
```  
iterator upper_bound(key_type key);  
```  
  
#### <a name="parameters"></a>매개 변수  
 key  
 검색할 키 값입니다.  
  
## <a name="remarks"></a>설명  
 멤버 함수는 마지막 요소를 결정 `X` 과 순서가 제어 된 시퀀스의 `key`합니다. 이러한 요소가 존재 하거나 `X` 는 제어 된 시퀀스의 마지막 요소 반환 [multiset:: end (STL/CLR)](../dotnet/multiset-end-stl-clr.md)`()`; 그렇지 않으면 의첫번째요소를지정하는반복기를반환`X`. 지정된 된 키와 일치 하는 제어 된 시퀀스의 현재 요소 시퀀스의 끝으로 이동 하려면 사용 합니다.  
  
## <a name="example"></a>예제  
  
```  
// cliext_multiset_upper_bound.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("upper_bound(L'x')==end() = {0}",   
        c1.upper_bound(L'x') == c1.end());   
  
    System::Console::WriteLine("*upper_bound(L'a') = {0}",   
        *c1.upper_bound(L'a'));   
    System::Console::WriteLine("*upper_bound(L'b') = {0}",   
        *c1.upper_bound(L'b'));   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
upper_bound(L'x')==end() = True  
*upper_bound(L'a') = b  
*upper_bound(L'b') = c  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/set >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [multiset (STL/CLR)](../dotnet/multiset-stl-clr.md)   
 [multiset:: count (STL/CLR)](../dotnet/multiset-count-stl-clr.md)   
 [multiset:: equal_range (STL/CLR)](../dotnet/multiset-equal-range-stl-clr.md)   
 [multiset:: find (STL/CLR)](../dotnet/multiset-find-stl-clr.md)   
 [multiset::lower_bound(STL/CLR)](../dotnet/multiset-lower-bound-stl-clr.md)