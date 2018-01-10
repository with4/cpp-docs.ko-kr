---
title: unary_delegate_noreturn (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::unary_delegate_noreturn
dev_langs: C++
helpviewer_keywords: unary_delegate_noreturn function [STL/CLR]
ms.assetid: 3c3fb143-f60f-4e28-a66b-690e3a7b2f9b
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 901fbb73305be96a6987928c5cf8c015f85781c3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="unarydelegatenoreturn-stlclr"></a>unary_delegate_noreturn(STL/CLR)
반환 하는 인수가 한 개인 대리자를 설명 하는 genereic 클래스 `void`합니다. 사용할 대리자의 인수 형식이 측면에서 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
generic<typename Arg>  
    delegate void unary_delegate_noreturn(Arg);  
```  
  
#### <a name="parameters"></a>매개 변수  
 Arg  
 인수 형식입니다.  
  
## <a name="remarks"></a>설명  
 Genereic 대리자에 반환 하는 단일 인수 함수에 설명 `void`합니다.  
  
 에 대 한는 note:  
  
 `unary_delegare_noreturn<int> Fun1;`  
  
 `unary_delegare_noreturn<int> Fun2;`  
  
 형식을 `Fun1` 및 `Fun2` 은 동의어 이며에 대 한 동안:  
  
 `delegate void Fun1(int);`  
  
 `delegate void Fun2(int);`  
  
 형식이 같은 하지 않습니다.  
  
## <a name="example"></a>예  
  
```  
// cliext_unary_delegate_noreturn.cpp   
// compile with: /clr   
#include <cliext/functional>   
  
void hash_val(wchar_t val)   
    {   
    System::Console::WriteLine("hash({0}) = {1}",   
       val, (val * 17 + 31) % 67);   
    }   
  
typedef cliext::unary_delegate_noreturn<wchar_t> Mydelegate;   
int main()   
    {   
    Mydelegate^ myhash = gcnew Mydelegate(&hash_val);   
  
    myhash(L'a');   
    myhash(L'b');   
    return (0);   
    }  
  
```  
  
```Output  
hash(a) = 5  
hash(b) = 22  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/기능 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [binary_delegate (STL/CLR)](../dotnet/binary-delegate-stl-clr.md)   
 [binary_delegate_noreturn (STL/CLR)](../dotnet/binary-delegate-noreturn-stl-clr.md)   
 [unary_delegate(STL/CLR)](../dotnet/unary-delegate-stl-clr.md)