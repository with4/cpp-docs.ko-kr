---
title: 'vector:: operator = (STL/CLR) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::vector::operator=
dev_langs: C++
helpviewer_keywords: operator= member [STL/CLR]
ms.assetid: c2de9d74-9de7-4560-866f-3d55952e9bd7
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 4aa930bcfb470a0fd76cc114d34a48e78ce66601
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="vectoroperator-stlclr"></a>vector::operator=(STL/CLR)
제어되는 시퀀스를 바꿉니다.  
  
## <a name="syntax"></a>구문  
  
```  
vector<Value>% operator=(vector<Value>% right);  
```  
  
#### <a name="parameters"></a>매개 변수  
 오른쪽  
 복사할 컨테이너입니다.  
  
## <a name="remarks"></a>설명  
 멤버 연산자 복사본 `right` 개체에 반환 `*this`합니다. 이를 사용하여 제어되는 시퀀스를 `right`의 제어되는 시퀀스 복사본으로 대체합니다.  
  
## <a name="example"></a>예  
  
```  
// cliext_vector_operator_as.cpp   
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
 **헤더:** \<cliext/벡터 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [vector (STL/CLR)](../dotnet/vector-stl-clr.md)   
 [vector::assign(STL/CLR)](../dotnet/vector-assign-stl-clr.md)