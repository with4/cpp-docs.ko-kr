---
title: 'multiset:: generic_reverse_iterator (STL/CLR) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::multiset::generic_reverse_iterator
dev_langs: C++
helpviewer_keywords: generic_reverse_iterator member [STL/CLR]
ms.assetid: 263808db-e25a-4092-8516-446a8821527e
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: db55d6fa43921dc87bf6d297766c65b88ff621ec
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="multisetgenericreverseiterator-stlclr"></a>multiset::generic_reverse_iterator(STL/CLR)
컨테이너에 대 한 제네릭 인터페이스와 함께 사용 하기 위해 한 반대 반복기의 형식입니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef Microsoft::VisualC::StlClr::Generic::  
    ReverseRandomAccessIterator<generic_value>  
    generic_reverse_iterator;  
```  
  
## <a name="remarks"></a>설명  
 형식은이 서식 파일 컨테이너 클래스에 대 한 제네릭 인터페이스와 함께 사용할 수 있는 제네릭 역방향 반복기를 설명 합니다.  
  
## <a name="example"></a>예  
  
```  
// cliext_multiset_generic_reverse_iterator.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct a generic container   
    Mymultiset::generic_container^ gc1 = %c1;   
    for each (wchar_t elem in gc1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// get an element and display it   
    Mymultiset::generic_reverse_iterator gcit = gc1->rbegin();   
    Mymultiset::generic_value gcval = *gcit;   
    System::Console::WriteLine(" {0}", gcval);   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
a b c  
c  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/set >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [multiset (STL/CLR)](../dotnet/multiset-stl-clr.md)   
 [multiset:: generic_container (STL/CLR)](../dotnet/multiset-generic-container-stl-clr.md)   
 [multiset::generic_iterator(STL/CLR)](../dotnet/multiset-generic-iterator-stl-clr.md)