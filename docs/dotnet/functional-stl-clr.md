---
title: 기능 (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- <cliext/functional>
dev_langs:
- C++
helpviewer_keywords:
- <functional> header [STL/CLR]
- <cliext/functional> header [STL/CLR]
- functional functions [STL/CLR]
ms.assetid: 88738b8c-5d37-4375-970e-a4442bf5efde
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 38bfbe025c92aa54956a165367b367cecc6160b2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="functional-stlclr"></a>functional(STL/CLR)
STL/CLR 헤더를 포함 `<cliext/functional>` 정의 하는 템플릿 클래스 및 관련된 템플릿 대리자 및 함수의 다양 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
#include <functional>  
```  
  
## <a name="declarations"></a>선언  
  
|대리자|설명|  
|--------------|-----------------|  
|[binary_delegate(STL/CLR)](../dotnet/binary-delegate-stl-clr.md)|두 인수 대리자입니다.|  
|[binary_delegate_noreturn(STL/CLR)](../dotnet/binary-delegate-noreturn-stl-clr.md)|반환 하는 두 인수 대리자 `void`합니다.|  
|[unary_delegate(STL/CLR)](../dotnet/unary-delegate-stl-clr.md)|인수가 한 개인 대리자입니다.|  
|[unary_delegate_noreturn(STL/CLR)](../dotnet/unary-delegate-noreturn-stl-clr.md)|반환 된 단일 인수 대리자 `void`합니다.|  
  
|클래스|설명|  
|-----------|-----------------|  
|[binary_negate(STL/CLR)](../dotnet/binary-negate-stl-clr.md)|두 인수 함수를 부정 하는 함수입니다.|  
|[binder1st(STL/CLR)](../dotnet/binder1st-stl-clr.md)|두 인수 함수에 첫 번째 인수를 바인딩할 함수입니다.|  
|[binder2nd(STL/CLR)](../dotnet/binder2nd-stl-clr.md)|두 인수 함수에 두 번째 인수를 바인딩할 함수입니다.|  
|[divides(STL/CLR)](../dotnet/divides-stl-clr.md)|함수를 나눕니다.|  
|[equal_to(STL/CLR)](../dotnet/equal-to-stl-clr.md)|같음 비교 함수입니다.|  
|[greater(STL/CLR)](../dotnet/greater-stl-clr.md)|큰 비교 함수입니다.|  
|[greater_equal(STL/CLR)](../dotnet/greater-equal-stl-clr.md)|크거나 같음 비교 함수입니다.|  
|[less(STL/CLR)](../dotnet/less-stl-clr.md)|덜 비교 함수입니다.|  
|[less_equal(STL/CLR)](../dotnet/less-equal-stl-clr.md)|작거나 같음 비교 함수입니다.|  
|[logical_and(STL/CLR)](../dotnet/logical-and-stl-clr.md)|논리 AND 함수입니다.|  
|[logical_not(STL/CLR)](../dotnet/logical-not-stl-clr.md)|논리 함수에 없습니다.|  
|[logical_or(STL/CLR)](../dotnet/logical-or-stl-clr.md)|논리 OR 함수입니다.|  
|[minus(STL/CLR)](../dotnet/minus-stl-clr.md)|함수를 뺍니다.|  
|[modulus(STL/CLR)](../dotnet/modulus-stl-clr.md)|모듈러스 함수입니다.|  
|[multiplies(STL/CLR)](../dotnet/multiplies-stl-clr.md)|곱하기 함수입니다.|  
|[negate(STL/CLR)](../dotnet/negate-stl-clr.md)|부정 되는 인수를 반환 하는 함수입니다.|  
|[not_equal_to(STL/CLR)](../dotnet/not-equal-to-stl-clr.md)|같지 않음 비교 함수입니다.|  
|[plus(STL/CLR)](../dotnet/plus-stl-clr.md)|함수를 추가 합니다.|  
|[unary_negate(STL/CLR)](../dotnet/unary-negate-stl-clr.md)|단일 인수 함수를 부정 하는 함수입니다.|  
  
|함수|설명|  
|--------------|-----------------|  
|[bind1st(STL/CLR)](../dotnet/bind1st-stl-clr.md)|인수 및 함수에 대 한 binder1st를 생성합니다.|  
|[bind2nd(STL/CLR)](../dotnet/bind2nd-stl-clr.md)|인수 및 함수에 대 한 binder2nd를 생성합니다.|  
|[not1(STL/CLR)](../dotnet/not1-stl-clr.md)|함수에 대 한 unary_negate를 생성합니다.|  
|[not1(STL/CLR)](../dotnet/not1-stl-clr.md)|함수에 대 한 binary_negate를 생성합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/기능 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [STL/CLR 라이브러리 참조](../dotnet/stl-clr-library-reference.md)