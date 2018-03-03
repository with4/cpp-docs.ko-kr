---
title: _variant_t::_variant_t | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _variant_t::_variant_t
dev_langs:
- C++
helpviewer_keywords:
- _variant_t class [C++], constructor
- _variant_t method [C++]
ms.assetid: a50e5b33-d4c6-4a26-8e7e-a0a25fd9895b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cd85a54e9f73352894f6575051fe1ea8be0698fb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="varianttvariantt"></a>_variant_t::_variant_t
**Microsoft 전용**  
  
 `_variant_t` 개체를 생성합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      _variant_t( ) throw( );  
  
_variant_t(  
   const VARIANT& varSrc   
);  
  
_variant_t(  
   const VARIANT* pVarSrc   
);  
  
_variant_t(  
   const _variant_t& var_t_Src   
);  
  
_variant_t(  
   VARIANT& varSrc,  
   bool fCopy   
);  
  
_variant_t(  
   short sSrc,  
   VARTYPE vtSrc = VT_I2   
);  
  
_variant_t(  
   long lSrc,  
   VARTYPE vtSrc = VT_I4   
);  
  
_variant_t(  
   float fltSrc   
) throw( );  
  
_variant_t(  
   double dblSrc,  
   VARTYPE vtSrc = VT_R8   
);  
  
_variant_t(  
   const CY& cySrc   
) throw( );  
  
_variant_t(  
   const _bstr_t& bstrSrc   
);  
  
_variant_t(  
   const wchar_t *wstrSrc   
);  
  
_variant_t(  
   const char* strSrc   
);  
  
_variant_t(  
   IDispatch* pDispSrc,  
   bool fAddRef = true   
) throw( );  
  
_variant_t(  
   bool bSrc   
) throw( );  
  
_variant_t(  
   IUnknown* pIUknownSrc,  
   bool fAddRef = true   
) throw( );  
  
_variant_t(  
   const DECIMAL& decSrc   
) throw( );  
  
_variant_t(  
   BYTE bSrc   
) throw( );  
  
variant_t(  
   char cSrc  
) throw();  
  
_variant_t(  
   unsigned short usSrc  
) throw();  
  
_variant_t(  
   unsigned long ulSrc  
) throw();  
  
_variant_t(  
   int iSrc  
) throw();  
  
_variant_t(  
   unsigned int uiSrc  
) throw();  
  
_variant_t(  
   __int64 i8Src  
) throw();  
  
_variant_t(  
   unsigned __int64 ui8Src  
) throw();  
```  
  
#### <a name="parameters"></a>매개 변수  
 *varSrc*  
 A **VARIANT** 새 복사할 개체 `_variant_t` 개체입니다.  
  
 *pVarSrc*  
 에 대 한 포인터는 **VARIANT** 새 복사할 개체 `_variant_t` 개체입니다.  
  
 *var_t_Src*  
 새 `_variant_t` 개체로 복사할 `_variant_t` 개체입니다.  
  
 `fCopy`  
 False 인 경우, 제공 된 **VARIANT** 에 새 개체를 연결 `_variant_t` 개체 하 여 새 복사본을 만들지 않고 **VariantCopy**합니다.  
  
 *ISrc, sSrc*  
 새 `_variant_t` 개체로 복사할 정수 값입니다.  
  
 `vtSrc`  
 **VARTYPE** 새 `_variant_t` 개체입니다.  
  
 *fltSrc, dblSrc*  
 새 `_variant_t` 개체에 복사될 숫자 값입니다.  
  
 `cySrc`  
 A **CY** 새 복사할 개체 `_variant_t` 개체입니다.  
  
 `bstrSrc`  
 새 `_bstr_t` 개체로 복사할 `_variant_t` 개체입니다.  
  
 *strSrc, wstrSrc*  
 새 `_variant_t` 개체로 복사할 문자열입니다.  
  
 `bSrc`  
 새 `bool` 개체로 복사할 `_variant_t` 값입니다.  
  
 `pIUknownSrc`  
 에 대 한 COM 인터페이스 포인터를 **VT_UNKNOWN** 개체를 새 개체로 캡슐화 될 `_variant_t` 개체입니다.  
  
 `pDispSrc`  
 에 대 한 COM 인터페이스 포인터를 **VT_DISPATCH** 개체를 새 개체로 캡슐화 될 `_variant_t` 개체입니다.  
  
 `decSrc`  
 A **10 진수** 새 복사 될 값을 `_variant_t` 개체입니다.  
  
 `bSrc`  
 A **바이트** 새 복사 될 값을 `_variant_t` 개체입니다.  
  
 `cSrc`  
 새 `char` 개체로 복사할 `_variant_t` 값입니다.  
  
 *usSrc*  
 A **부호 없는 short** 새 복사 될 값을 `_variant_t` 개체입니다.  
  
 *ulSrc*  
 새 `unsigned long` 개체로 복사할 `_variant_t` 값입니다.  
  
 `iSrc`  
 새 `int` 개체로 복사할 `_variant_t` 값입니다.  
  
 *uiSrc*  
 새 `unsigned int` 개체로 복사할 `_variant_t` 값입니다.  
  
 *i8Src*  
 __**Int64** 새 복사 될 값을 `_variant_t` 개체입니다.  
  
 *ui8Src*  
 **unsigned __int64** 새 복사 될 값을 `_variant_t` 개체입니다.  
  
## <a name="remarks"></a>설명  
  
-   **_variant_t ()** 빈 생성 `_variant_t` 개체 `VT_EMPTY`합니다.  
  
-   **_variant_t (VARIANT &***varSrc***)** 생성 한 `_variant_t` 개체의 복사본에서는 **VARIANT** 개체입니다. 변형 형식이 유지됩니다.  
  
-   **_variant_t (VARIANT\****pVarSrc***)** 생성 한 `_variant_t` 개체의 복사본에서는 **VARIANT** 개체입니다. 변형 형식이 유지됩니다.  
  
-   **_variant_t (_variant_t &***var_t_Src***)** 생성 한 `_variant_t` 개체에서 다른 `_variant_t` 개체입니다. 변형 형식이 유지됩니다.  
  
-   **_variant_t (VARIANT &***varSrc* **, bool**`fCopy`**)** 생성 한 `_variant_t` 기존 개체  **VARIANT** 개체입니다. 경우 `fCopy` 은 **false**, **VARIANT** 개체 복사본을 만들지 않고 새 개체에 연결 됩니다.  
  
-   **_variant_t (짧은***sSrc* **, VARTYPE**`vtSrc`**VT_I2 =)** 생성 한 `_variant_t` 형식의 개체 `VT_I2` 또는 `VT_BOOL` 에서 **짧은** 정수 값입니다. 다른 모든 **VARTYPE** 결과 `E_INVALIDARG` 오류입니다.  
  
-   **_variant_t (긴** `lSrc` **, VARTYPE**`vtSrc`**VT_I4 =)** 생성 한 `_variant_t` 형식의 개체 `VT_I4`, `VT_BOOL`, 또는 `VT_ERROR` 에서 **긴** 정수 값입니다. 다른 모든 **VARTYPE** 결과 `E_INVALIDARG` 오류입니다.  
  
-   **_variant_t (float**`fltSrc`**)** 생성 한 `_variant_t` 형식의 개체 `VT_R4` 에서 **float** 숫자 값입니다.  
  
-   **_variant_t (이중** `dblSrc` **, VARTYPE**`vtSrc`**VT_R8 =)** 생성 한 `_variant_t` 형식의 개체 `VT_R8` 또는 `VT_DATE` 는 에서**double** 숫자 값입니다. 다른 모든 **VARTYPE** 결과 `E_INVALIDARG` 오류입니다.  
  
-   **_variant_t (CY &**`cySrc`**)** 생성 한 `_variant_t` 형식의 개체 `VT_CY` 에서 **CY** 개체입니다.  
  
-   **_variant_t (_bstr_t &**`bstrSrc`**)** 생성 한 `_variant_t` 형식의 개체 `VT_BSTR` 에서 `_bstr_t` 개체입니다. 새 `BSTR`이 할당됩니다.  
  
-   **_variant_t (wchar_t \***  *wstrSrc***)** 생성 한 `_variant_t` 형식의 개체 `VT_BSTR` 유니코드 문자열에서입니다. 새 `BSTR`이 할당됩니다.  
  
-   **_variant_t (char\***`strSrc`**)** 생성 한 `_variant_t` 형식의 개체 `VT_BSTR` 문자열에서입니다. 새 `BSTR`이 할당됩니다.  
  
-   **_variant_t (bool**`bSrc`**)** 생성 한 `_variant_t` 형식의 개체 `VT_BOOL` 에서 `bool` 값입니다.  
  
-   **_variant_t (IUnknown\***  `pIUknownSrc` **, bool**`fAddRef`**= true)** 생성 한 `_variant_t` 형식의 개체 **VT_UNKNOWN**  COM 인터페이스 포인터에서. 경우 `fAddRef` 은 **true**, 다음 `AddRef` 는 일치에 대 한 호출에 제공 된 인터페이스 포인터에서 호출 **릴리스** 는 발생 하는 때는 `_variant_t` 개체를 제거 합니다. 호출 하 여은 **릴리스** 에 제공된 된 인터페이스 포인터입니다. 경우 `fAddRef` 은 **false**,이 생성자는 제공된 된 인터페이스 포인터의 소유권; 호출 하지 않으면 **릴리스** 제공된 된 인터페이스 포인터에 있습니다.  
  
-   **_variant_t (IDispatch\***  `pDispSrc` **, bool**`fAddRef`**= true)** 생성 한 `_variant_t` 형식의 개체 **VT_DISPATCH**  COM 인터페이스 포인터에서. 경우 `fAddRef` 은 **true**, 다음 `AddRef` 는 일치에 대 한 호출에 제공 된 인터페이스 포인터에서 호출 **릴리스** 는 발생 하는 때는 `_variant_t` 개체를 제거 합니다. 호출 하 여은 **릴리스** 에 제공된 된 인터페이스 포인터입니다. 경우 **fAddRef** 가 false 이면이 생성자는 제공된 된 인터페이스 포인터의 소유권; 호출 하지 않으면 **릴리스** 제공된 된 인터페이스 포인터에 합니다.  
  
-   **_variant_t (10 진수 &**`decSrc`**)** 생성 한 `_variant_t` 형식의 개체 **VT_DECIMAL** 에서 **10 진수** 값입니다.  
  
-   **_variant_t (바이트**`bSrc`**)** 생성 한 `_variant_t` 형식의 개체 `VT_UI1` 에서 **바이트** 값입니다.  
  
 **Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [_variant_t 클래스](../cpp/variant-t-class.md)