---
title: 'vector:: assign (STL/CLR) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::vector::assign
dev_langs:
- C++
helpviewer_keywords:
- assign member [STL/CLR]
ms.assetid: 945e2048-6c61-4701-b13c-8241cbee3fa1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: a16e9262ad69f6f4fe2e11030b5880485139823a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="vectorassign-stlclr"></a>vector::assign(STL/CLR)
모든 요소를 바꿉니다.  
  
## <a name="syntax"></a>구문  
  
```  
void assign(size_type count, value_type val);  
template<typename InIt>  
    void assign(InIt first, InIt last);  
void assign(System::Collections::Generic::IEnumerable<Value>^ right);  
```  
  
#### <a name="parameters"></a>매개 변수  
 count  
 삽입할 요소의 수입니다.  
  
 첫 번째  
 삽입할 범위의의 시작입니다.  
  
 last  
 삽입할 범위의 끝입니다.  
  
 오른쪽  
 삽입 하는 열거형입니다.  
  
 val  
 삽입할 요소의 값입니다.  
  
## <a name="remarks"></a>설명  
 첫 번째 멤버 함수는 반복 된 제어 되는 시퀀스 바꿉니다 `count` 값의 요소 `val`합니다. 하면을 채우는 데 사용할 컨테이너 요소와 동일한 값이 모두 포함 합니다.  
  
 경우 `InIt` 정수 형식, 두 번째 멤버 함수는 동일 하 게 동작 `assign((size_type)first, (value_type)last)`합니다. 제어 되는 순서와 대체 그렇지 않으면 [`first`, `last`). 사용할 있습니다 제어 된 시퀀스 복사본 되도록 다른 시퀀스.  
  
 열거자에 지정 된 시퀀스와 제어 된 시퀀스를 대체 하는 세 번째 멤버 함수 `right`합니다. 제어 되는 시퀀스의 사본을 열거형에서 설명 하는 순서를 사용 합니다.  
  
## <a name="example"></a>예제  
  
```  
// cliext_vector_assign.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// assign a repetition of values   
    cliext::vector<wchar_t> c2;   
    c2.assign(6, L'x');   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign an iterator range   
    c2.assign(c1.begin(), c1.end() - 1);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign an enumeration   
    c2.assign(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c1);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
x x x x x x  
a b  
a b c  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/벡터 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [vector (STL/CLR)](../dotnet/vector-stl-clr.md)   
 [vector::operator=(STL/CLR)](../dotnet/vector-operator-assign-stl-clr.md)