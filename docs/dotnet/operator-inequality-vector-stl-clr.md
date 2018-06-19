---
title: operator! = (vector) (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::vector::operator!=
dev_langs:
- C++
helpviewer_keywords:
- operator!= member [STL/CLR]
ms.assetid: 6f7b0569-b2d1-4f36-8520-31839bf6db9b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: de581c52362faf0fb9583d79238f3bb0974d0d26
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33139647"
---
# <a name="operator-vector-stlclr"></a>operator!= (vector)(STL/CLR)
같지 않음 비교를 벡터입니다.  
  
## <a name="syntax"></a>구문  
  
```  
template<typename Value>  
    bool operator!=(vector<Value>% left,  
        vector<Value>% right);  
```  
  
#### <a name="parameters"></a>매개 변수  
 왼쪽  
 비교할 왼쪽 컨테이너입니다.  
  
 오른쪽  
 비교할 오른쪽 컨테이너입니다.  
  
## <a name="remarks"></a>설명  
 연산자 함수 반환 `!(left == right)`합니다. 테스트를 사용 하는지 여부를 `left` 동일 정렬 되지 않은 `right` 두 벡터 요소에서 비교 된 요소를가 하는 경우.  
  
## <a name="example"></a>예제  
  
```  
// cliext_vector_operator_ne.cpp   
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
  
    System::Console::WriteLine("[a b c] != [a b c] is {0}",   
        c1 != c1);   
    System::Console::WriteLine("[a b c] != [a b d] is {0}",   
        c1 != c2);   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
 a b d  
[a b c] != [a b c] is False  
[a b c] != [a b d] is True  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/벡터 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [vector (STL/CLR)](../dotnet/vector-stl-clr.md)   
 [연산자 = = (vector) (STL/CLR)](../dotnet/operator-equality-vector-stl-clr.md)   
 [연산자\< (vector) (STL/CLR)](../dotnet/operator-less-than-vector-stl-clr.md)   
 [연산자 > = (vector) (STL/CLR)](../dotnet/operator-greater-or-equal-vector-stl-clr.md)   
 [연산자 > (vector) (STL/CLR)](../dotnet/operator-greater-than-vector-stl-clr.md)   
 [operator<= (vector)(STL/CLR)](../dotnet/operator-less-or-equal-vector-stl-clr.md)