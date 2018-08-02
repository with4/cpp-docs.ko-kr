---
title: _variant_t::operator = | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _variant_t::operator=
dev_langs:
- C++
helpviewer_keywords:
- operator= [C++], variant
- operator = [C++], variant
- = operator [C++], with specific Visual C++ objects
ms.assetid: 77622723-6e49-4dec-9e0f-fa74028f1a3c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d757c645ae131b88ffb99e571d1e08214eda8129
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39462867"
---
# <a name="varianttoperator-"></a>_variant_t::operator =
**Microsoft 전용**  
  
## <a name="syntax"></a>구문  
  
```  
_variant_t& operator=(  
   const VARIANT& varSrc   
);  
  
_variant_t& operator=(  
   const VARIANT* pVarSrc   
);  
  
_variant_t& operator=(  
   const _variant_t& var_t_Src   
);  
  
_variant_t& operator=(  
   short sSrc   
);  
  
_variant_t& operator=(  
   long lSrc   
);  
  
_variant_t& operator=(  
   float fltSrc   
);  
  
_variant_t& operator=(  
   double dblSrc   
);  
  
_variant_t& operator=(  
   const CY& cySrc   
);  
  
_variant_t& operator=(  
   const _bstr_t& bstrSrc   
);  
  
_variant_t& operator=(  
   const wchar_t* wstrSrc   
);  
  
_variant_t& operator=(  
   const char* strSrc   
);  
  
_variant_t& operator=(  
   IDispatch* pDispSrc   
);  
  
_variant_t& operator=(  
   bool bSrc   
);  
  
_variant_t& operator=(  
   IUnknown* pSrc   
);  
  
_variant_t& operator=(  
   const DECIMAL& decSrc   
);  
  
_variant_t& operator=(  
   BYTE bSrc   
);  
  
_variant_t& operator=(  
   char cSrc  
);  
  
_variant_t& operator=(  
   unsigned short usSrc  
);  
  
_variant_t& operator=(  
   unsigned long ulSrc  
);  
  
_variant_t& operator=(  
   int iSrc  
);  
  
_variant_t& operator=(  
   unsigned int uiSrc  
);  
  
_variant_t& operator=(  
   __int64 i8Src  
);  
  
_variant_t& operator=(  
   unsigned __int64 ui8Src  
);  
```  
  
## <a name="remarks"></a>설명  
 다음 연산자는 `_variant_t` 개체에 새 값을 할당합니다.  
  
-   **operator = (***varSrc***)** 기존 할당 `VARIANT` 에 `_variant_t` 개체입니다.  
  
-   **operator = (***pVarSrc***)** 기존 할당 `VARIANT` 에 `_variant_t` 개체입니다.  
  
-   **operator = (***var_t_Src***)** 기존 할당 `_variant_t` 개체를 `_variant_t` 개체입니다.      
  
-   **연산자 = (***sSrc***)** 할당 된 **짧은** 정수 값을 `_variant_t` 개체입니다.  
  
-   **연산자 = (**`lSrc`**)** 할당 한 **긴** 정수 값을 `_variant_t` 개체입니다.  
  
-   **연산자 = (***fltSrc***)** 할당 된 **float** 숫자 값을 `_variant_t` 개체입니다.  
  
-   **연산자 = (***dblSrc***)** 할당 한 **double** 숫자 값을 `_variant_t` 개체입니다.  
  
-   **operator = (***cySrc***)** 할당을 `CY` 개체를 `_variant_t` 개체.  
  
-   **operator = (***bstrSrc***)** 할당을 `BSTR` 개체를 `_variant_t` 개체.  
  
-   **operator = (***wstrSrc***)** 유니코드 문자열을 할당을 `_variant_t` 개체입니다.  
  
-   **operator = (**`strSrc`**)** 멀티 바이트 문자열을 할당을 `_variant_t` 개체입니다.  
  
-   **연산자 = (** `bSrc` **)** 할당 한 **bool** 값을 `_variant_t` 개체입니다.  
  
-   **operator = (***pDispSrc***)** 할당을 `VT_DISPATCH` 개체를 `_variant_t` 개체.  
  
-   **operator = (***pIUnknownSrc***)** 할당을 `VT_UNKNOWN` 개체를 `_variant_t` 개체.  
  
-   **연산자 = (***decSrc***)** 할당 된 `DECIMAL` 값을 `_variant_t` 개체입니다.  
  
-   **연산자 = (** `bSrc` **)** 할당 한 `BYTE` 값을 `_variant_t` 개체입니다.  
  
 **Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고자료  
 [_variant_t 클래스](../cpp/variant-t-class.md)