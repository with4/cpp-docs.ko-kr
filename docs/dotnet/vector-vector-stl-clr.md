---
title: 'vector:: vector (STL/CLR) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::vector::vector
dev_langs:
- C++
helpviewer_keywords:
- vector member [STL/CLR]
ms.assetid: a0b5e807-1ef2-422b-b772-1f96cd62fb51
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: f6921428c43ccc46b28b14523f8b17fff9185453
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33172568"
---
# <a name="vectorvector-stlclr"></a>vector::vector(STL/CLR)
컨테이너 개체를 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```  
vector();  
vector(vector<Value>% right);  
vector(vector<Value>^ right);  
explicit vector(size_type count);  
vector(size_type count, value_type val);  
template<typename InIt>  
    vector(InIt first, InIt last);  
vector(System::Collections::Generic::IEnumerable<Value>^ right);  
```  
  
#### <a name="parameters"></a>매개 변수  
 count  
 삽입할 요소의 수입니다.  
  
 첫 번째  
 삽입할 범위의의 시작입니다.  
  
 last  
 삽입할 범위의 끝입니다.  
  
 오른쪽  
 삽입할 개체 또는 범위입니다.  
  
 val  
 삽입할 요소의 값입니다.  
  
## <a name="remarks"></a>설명  
 생성자:  
  
 `vector();`  
  
 요소가 없는 제어 되는 시퀀스를 초기화합니다. 초기는 빈 제어 시퀀스를 지정 하려면 사용 합니다.  
  
 생성자:  
  
 `vector(vector<Value>% right);`  
  
 순서와 제어 된 시퀀스를 초기화 합니다. [`right.begin()`, `right.end()`). 벡터 개체에 의해 제어 되는 시퀀스의 복사본 인는 초기 제어 시퀀스를 지정 하려면 사용할 `right`합니다.  
  
 생성자:  
  
 `vector(vector<Value>^ right);`  
  
 순서와 제어 된 시퀀스를 초기화 합니다. [`right->begin()`, `right->end()`). 핸들은 벡터 개체에 의해 제어 되는 시퀀스의 복사본 인는 초기 제어 시퀀스를 지정 하려면 사용할 `right`합니다.  
  
 생성자:  
  
 `explicit vector(size_type count);`  
  
 이 있는 제어 된 시퀀스를 초기화 `count` 각 요소 값을 가진 `value_type()`합니다. 있습니다을 채우는 데 사용할 컨테이너 요소와 모든 기본 값이 포함 됩니다.  
  
 생성자:  
  
 `vector(size_type count, value_type val);`  
  
 이 있는 제어 된 시퀀스를 초기화 `count` 각 요소 값을 가진 `val`합니다. 하면을 채우는 데 사용할 컨테이너 요소와 동일한 값이 모두 포함 합니다.  
  
 생성자:  
  
 `template<typename InIt>`  
  
 `vector(InIt first, InIt last);`  
  
 순서와 제어 된 시퀀스를 초기화 합니다. [`first`, `last`). 제어 되는 시퀀스의 사본을 다른 시퀀스를 사용 합니다.  
  
 생성자:  
  
 `vector(System::Collections::Generic::IEnumerable<Value>^ right);`  
  
 열거자에 지정 된 시퀀스와 제어 된 시퀀스를 초기화 `right`합니다. 제어 되는 시퀀스의 사본을 열거자에서 설명 하는 다른 시퀀스를 사용 합니다.  
  
## <a name="example"></a>예제  
  
```  
// cliext_vector_construct.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
// construct an empty container   
    cliext::vector<wchar_t> c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// construct with a repetition of default values   
    cliext::vector<wchar_t> c2(3);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", (int)elem);   
    System::Console::WriteLine();   
  
// construct with a repetition of values   
    cliext::vector<wchar_t> c3(6, L'x');   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range   
    cliext::vector<wchar_t>::iterator it = c3.end();   
    cliext::vector<wchar_t> c4(c3.begin(), --it);   
    for each (wchar_t elem in c4)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an enumeration   
    cliext::vector<wchar_t> c5(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3);   
    for each (wchar_t elem in c5)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    cliext::vector<wchar_t> c7(c3);   
    for each (wchar_t elem in c7)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying a container handle   
    cliext::vector<wchar_t> c8(%c3);   
    for each (wchar_t elem in c8)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    return (0);   
    }  
  
```  
  
```Output  
size() = 0  
 0 0 0  
 x x x x x x  
 x x x x x  
 x x x x x x  
 x x x x x x  
 x x x x x x  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/벡터 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [vector (STL/CLR)](../dotnet/vector-stl-clr.md)   
 [vector:: assign (STL/CLR)](../dotnet/vector-assign-stl-clr.md)   
 [vector:: generic_container (STL/CLR)](../dotnet/vector-generic-container-stl-clr.md)   
 [vector::operator=(STL/CLR)](../dotnet/vector-operator-assign-stl-clr.md)