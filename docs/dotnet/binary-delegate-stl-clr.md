---
title: binary_delegate (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::binary_delegate
dev_langs:
- C++
helpviewer_keywords:
- binary_delegate function [STL/CLR]
ms.assetid: 52a9291a-e354-4b9e-a035-78dac1179ec5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: cdca27b416f8e721a44b475d115ac902696b4a85
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33105766"
---
# <a name="binarydelegate-stlclr"></a>binary_delegate(STL/CLR)
Genereic 클래스는 두 인수 대리자를 설명합니다. 사용 하면 대리자를 해당 인수 및 반환 형식으로 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
generic<typename Arg1,  
    typename Arg2,  
    typename Result>  
    delegate Result binary_delegate(Arg1, Arg2);  
```  
  
#### <a name="parameters"></a>매개 변수  
 arg1  
 첫 번째 인수의 형식입니다.  
  
 arg2  
 두 번째 인수의 형식입니다.  
  
 결과  
 반환 형식입니다.  
  
## <a name="remarks"></a>설명  
 Genereic 대리자는 두 인수 함수를 설명합니다.  
  
 에 대 한는 note:  
  
 `binary_delegate<int, int, int> Fun1;`  
  
 `binary_delegate<int, int, int> Fun2;`  
  
 형식을 `Fun1` 및 `Fun2` 은 동의어 이며에 대 한 동안:  
  
 `delegate int Fun1(int, int);`  
  
 `delegate int Fun2(int, int);`  
  
 형식이 같은 하지 않습니다.  
  
## <a name="example"></a>예제  
  
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
  
```Output  
compare(L'a', L'a') = False  
compare(L'a', L'b') = True  
compare(L'b', L'a') = False  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/기능 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [binary_delegate_noreturn (STL/CLR)](../dotnet/binary-delegate-noreturn-stl-clr.md)   
 [unary_delegate (STL/CLR)](../dotnet/unary-delegate-stl-clr.md)   
 [unary_delegate_noreturn(STL/CLR)](../dotnet/unary-delegate-noreturn-stl-clr.md)