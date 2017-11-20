---
title: "_variant_t 추출기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _variant_t.operatordouble
- operatorlong
- _variant_t::operator_bstr_t
- operatordouble
- _variant_t.operatorCY
- operatorCY
- _variant_t::operatorCY
- _variant_t::operatordouble
- operatorfloat
- operatorBYTE
- _variant_t.operatorDECIMAL
- _variant_t::operatorlong
- operatorIDispatch
- _variant_t.operatorBYTE
- operatorDECIMAL
- _variant_t.operator_bstr_t
- _variant_t::operatorDECIMAL
- _variant_t.operatorIUnknown
- _variant_t.operatorlong
- _variant_t::operatorIDispatch
- _variant_t::operatorIUnknown
- operatorIUnknown
- _variant_t.operatorbool
- _variant_t::operatorBYTE
- _variant_t.operatorfloat
- operator_bstr_t
- _variant_t::operatorbool
- operatorshort
- _variant_t::operatorshort
- _variant_t::operatorfloat
- _variant_t.operatorIDispatch
- _variant_t.operatorshort
dev_langs: C++
helpviewer_keywords:
- extractors, _variant_t class
- operator CY
- operator IDispatch
- operator SHORT
- operator double
- operator long
- operator _bstr_t
- operator DECIMAL
- operator float
- operator bool
- operator BYTE
- operator IUnknown
ms.assetid: 33c1782f-045a-4673-9619-1d750efc83a9
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 4db692b4847bf6a8aa7fb1ffca3f4a2d96de833c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="variantt-extractors"></a>_variant_t Extractors
**Microsoft 전용**  
  
 캡슐화 된 데이터를 추출 **VARIANT** 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```  
operator short( ) const;   
operator long( ) const;   
operator float( ) const;   
operator double( ) const;   
operator CY( ) const;   
operator _bstr_t( ) const;   
operator IDispatch*( ) const;   
operator bool( ) const;   
operator IUnknown*( ) const;   
operator DECIMAL( ) const;   
operator BYTE( ) const;  
operator VARIANT() const throw();  
operator char() const;  
operator unsigned short() const;  
operator unsigned long() const;  
operator int() const;  
operator unsigned int() const;  
operator __int64() const;  
operator unsigned __int64() const;  
```  
  
## <a name="remarks"></a>설명  
 캡슐화 된 원시 데이터를 추출 **VARIANT**합니다. 경우는 **VARIANT** 가 올바른 형식이 이미 **VariantChangeType** 변환을 시도 하는 데 사용 되 고 실패 시 오류가 생성 됩니다:  
  
-   **연산자 short ()** 추출는 **짧은** 정수 값입니다.  
  
-   **연산자 long ()** 추출는 **긴** 정수 값입니다.  
  
-   **연산자 float ()** 추출는 **float** 숫자 값입니다.  
  
-   **연산자 double ()** 추출는 **double** 정수 값입니다.  
  
-   **연산자 CY ()** 추출는 **CY** 개체입니다.  
  
-   **연산자 bool ()** 추출는 `bool` 값입니다.  
  
-   **연산자 DECIMAL ()** 추출는 **10 진수** 값입니다.  
  
-   **연산자 BYTE ()** 추출는 **바이트** 값입니다.  
  
-   **연산자 _bstr_t ()** 에 캡슐화 된 문자열을 추출 하는 `_bstr_t` 개체입니다.  
  
-   **연산자 IDispatch\*()** 캡슐화 된에서 dispinterface 포인터를 추출 **VARIANT**합니다. `AddRef`결과 포인터에서 호출 호출 하 여 되므로 **릴리스** 메모리를 해제 해야 합니다.  
  
-   **연산자 IUnknown\*()** 에서 캡슐화 된 COM 인터페이스 포인터를 추출 **VARIANT**합니다. `AddRef`결과 포인터에서 호출 호출 하 여 되므로 **릴리스** 메모리를 해제 해야 합니다.  
  
 **Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [_variant_t 클래스](../cpp/variant-t-class.md)
