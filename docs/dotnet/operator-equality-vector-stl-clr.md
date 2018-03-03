---
title: "연산자 = = (vector) (STL/CLR) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::vector::operator==
dev_langs:
- C++
helpviewer_keywords:
- operator== member [STL/CLR]
ms.assetid: b552c9a1-8d06-4090-b394-d08a84947594
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 860f25b0d38f6689927eebd5cb1359d33d03332d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="operator-vector-stlclr"></a>operator== (vector)(STL/CLR)
벡터 같은지 비교 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
template<typename Value>  
    bool operator==(vector<Value>% left,  
        vector<Value>% right);  
```  
  
#### <a name="parameters"></a>매개 변수  
 왼쪽  
 비교할 왼쪽 컨테이너입니다.  
  
 오른쪽  
 비교할 오른쪽 컨테이너입니다.  
  
## <a name="remarks"></a>설명  
 연산자 함수는 시퀀스에 의해 제어 하는 경우에 true를 반환 `left` 및 `right` 동일한 길이 및 각 위치에 대 한 `i`, `left[i] ==` `right[i]`합니다. 테스트를 사용 하는지 여부를 `left` 와 동일 하 게 정렬 되 `right` 두 벡터 요소에서 비교 된 요소를가 하는 경우.  
  
## <a name="example"></a>예  
  
```  
// cliext_vector_operator_eq.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    cliext::vector<wchar_t> c2;   
    c2.push_back(L'a');   
    c2.push_back(L'b');   
    c2.push_back(L'd');   
  
// display contents " a b d"   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("[a b c] == [a b c] is {0}",   
        c1 == c1);   
    System::Console::WriteLine("[a b c] == [a b d] is {0}",   
        c1 == c2);   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
 a b d  
[a b c] == [a b c] is True  
[a b c] == [a b d] is False  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/벡터 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [vector (STL/CLR)](../dotnet/vector-stl-clr.md)   
 [operator! = (vector) (STL/CLR)](../dotnet/operator-inequality-vector-stl-clr.md)   
 [연산자\< (vector) (STL/CLR)](../dotnet/operator-less-than-vector-stl-clr.md)   
 [연산자 > = (vector) (STL/CLR)](../dotnet/operator-greater-or-equal-vector-stl-clr.md)   
 [연산자 > (vector) (STL/CLR)](../dotnet/operator-greater-than-vector-stl-clr.md)   
 [operator<= (vector)(STL/CLR)](../dotnet/operator-less-or-equal-vector-stl-clr.md)