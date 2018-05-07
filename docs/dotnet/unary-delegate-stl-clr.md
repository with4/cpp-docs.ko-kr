---
title: unary_delegate (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::unary_delegate
dev_langs:
- C++
helpviewer_keywords:
- unary_delegate function [STL/CLR]
ms.assetid: b3ee253c-98e8-466e-a272-505e47aed061
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 689fc3afba26d4b20816f3513262b6c1fc269e2e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="unarydelegate-stlclr"></a>unary_delegate(STL/CLR)
Genereic 클래스는 단일 인수 대리자를 설명합니다. 사용 하면 대리자를 해당 인수 및 반환 형식으로 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
generic<typename Arg,  
    typename Result>  
    delegate Result unary_delegate(Arg);  
```  
  
#### <a name="parameters"></a>매개 변수  
 Arg  
 인수 형식입니다.  
  
 결과  
 반환 형식입니다.  
  
## <a name="remarks"></a>설명  
 Genereic 대리자는 단일 인수 함수를 설명합니다.  
  
 에 대 한는 note:  
  
 `unary_delegare<int, int> Fun1;`  
  
 `unary_delegare<int, int> Fun2;`  
  
 형식을 `Fun1` 및 `Fun2` 은 동의어 이며에 대 한 동안:  
  
 `delegate int Fun1(int);`  
  
 `delegate int Fun2(int);`  
  
 형식이 같은 하지 않습니다.  
  
## <a name="example"></a>예제  
  
```  
// cliext_unary_delegate.cpp   
// compile with: /clr   
#include <cliext/functional>   
  
int hash_val(wchar_t val)   
    {   
    return ((val * 17 + 31) % 67);   
    }   
  
typedef cliext::unary_delegate<wchar_t, int> Mydelegate;   
int main()   
    {   
    Mydelegate^ myhash = gcnew Mydelegate(&hash_val);   
  
    System::Console::WriteLine("hash(L'a') = {0}", myhash(L'a'));   
    System::Console::WriteLine("hash(L'b') = {0}", myhash(L'b'));   
    return (0);   
    }  
  
```  
  
```Output  
hash(L'a') = 5  
hash(L'b') = 22  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/기능 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [binary_delegate (STL/CLR)](../dotnet/binary-delegate-stl-clr.md)   
 [binary_delegate_noreturn (STL/CLR)](../dotnet/binary-delegate-noreturn-stl-clr.md)   
 [unary_delegate_noreturn(STL/CLR)](../dotnet/unary-delegate-noreturn-stl-clr.md)