---
title: "binary_delegate(STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::binary_delegate"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "binary_delegate 함수[STL/CLR]"
ms.assetid: 52a9291a-e354-4b9e-a035-78dac1179ec5
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# binary_delegate(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The genereic class describes a two\-argument delegate.  You use it specify a delegate in terms of its argument and return types.  
  
## 구문  
  
```  
generic<typename Arg1,  
    typename Arg2,  
    typename Result>  
    delegate Result binary_delegate(Arg1, Arg2);  
```  
  
#### 매개 변수  
 Arg1  
 The type of the first argument.  
  
 Arg2  
 The type of the second argument.  
  
 결과  
 반환 형식입니다.  
  
## 설명  
 The genereic delegate describes a two\-argument function.  
  
 Note that for:  
  
 `binary_delegate<int, int, int> Fun1;`  
  
 `binary_delegate<int, int, int> Fun2;`  
  
 the types `Fun1` and `Fun2` are synonyms, while for:  
  
 `delegate int Fun1(int, int);`  
  
 `delegate int Fun2(int, int);`  
  
 they are not the same type.  
  
## 예제  
  
```  
// cliext_binary_delegate.cpp   
// compile with: /clr   
#include <cliext/functional>   
  
bool key_compare(wchar_t left, wchar_t right)   
    {   
    return (left < right);   
    }   
  
typedef cliext::binary_delegate<wchar_t, wchar_t, bool> Mydelegate;   
int main()   
    {   
    Mydelegate^ kcomp = gcnew Mydelegate(&key_compare);   
  
    System::Console::WriteLine("compare(L'a', L'a') = {0}",   
        kcomp(L'a', L'a'));   
    System::Console::WriteLine("compare(L'a', L'b') = {0}",   
        kcomp(L'a', L'b'));   
    System::Console::WriteLine("compare(L'b', L'a') = {0}",   
        kcomp(L'b', L'a'));   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **compare\(L'a', L'a'\) \= False**  
**compare\(L'a', L'b'\) \= True**  
**compare\(L'b', L'a'\) \= False**   
## 요구 사항  
 **Header:** \<cliext\/functional\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [binary\_delegate\_noreturn](../dotnet/binary-delegate-noreturn-stl-clr.md)   
 [unary\_delegate](../dotnet/unary-delegate-stl-clr.md)   
 [unary\_delegate\_noreturn](../dotnet/unary-delegate-noreturn-stl-clr.md)