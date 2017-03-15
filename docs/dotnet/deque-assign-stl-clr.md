---
title: "deque::assign(STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::deque::assign"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "assign 멤버[STL/CLR]"
ms.assetid: 03fafdbb-6b10-4464-b3dc-0cc5cb8ac980
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# deque::assign(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

모든 요소를 바꿉니다.  
  
## 구문  
  
```  
void assign(size_type count, value_type val);  
template<typename InIt>  
    void assign(InIt first, InIt last);  
void assign(System::Collections::Generic::IEnumerable<Value>^ right);  
```  
  
#### 매개 변수  
 count  
 삽입할 요소의 개수입니다.  
  
 first  
 삽입할 범위의 시작입니다.  
  
 last  
 삽입할 범위의 끝입니다.  
  
 right  
 삽입할 열거형입니다.  
  
 val  
 삽입할 요소의 값입니다.  
  
## 설명  
 두 번째 멤버 함수는 `count` 에 의해 제어되는 시퀀스를  값의 `val` 요소의 반복으로 대체합니다.  채우는 데 사용할 컨테이너 요소와 같은 값을 갖는 모든것을 사용합니다.  
  
 `InIt`  가 정수 형식인 경우, 셋째 멤버 함수는 `assign((size_type)``first``, (value_type)``last``)`처럼 작동합니다.  제어되는 시퀀스를 `[``first``,` `last``)` 시퀀스로 바꿉니다.  사용 하면 그 제어 시퀀스 복사본을 다른 시퀀스입니다.  
  
 셋째 멤버 함수 열거자가 지정 된 시퀀스를 사용 하 여 제어 되는 시퀀스 대체  `right` 합니다.  제어 되는 시퀀스의 사본을 열거형에서 설명 하는 순서를 사용 합니다.  
  
## 예제  
  
```  
// cliext_deque_assign.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// assign a repetition of values   
    cliext::deque<wchar_t> c2;   
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
  
  **x x x x x x**  
 **a b**  
 **a b c**   
## 요구 사항  
 **Header:** \<cliext\/deque\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [deque](../dotnet/deque-stl-clr.md)   
 [operator\= \(deque\)](../dotnet/operator-assign-deque-stl-clr.md)