---
title: "_variant_t::_variant_t | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_variant_t::_variant_t"
  - "_variant_t._variant_t"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_variant_t 클래스, 생성자"
  - "_variant_t 메서드"
ms.assetid: a50e5b33-d4c6-4a26-8e7e-a0a25fd9895b
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# _variant_t::_variant_t
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 `_variant_t` 개체를 생성합니다.  
  
## 구문  
  
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
  
#### 매개 변수  
 *varSrc*  
 새 `_variant_t` 개체로 복사할 **VARIANT** 개체입니다.  
  
 *pVarSrc*  
 새 `_variant_t` 개체로 복사할 **VARIANT** 개체에 대한 포인터입니다.  
  
 *var\_t\_Src*  
 새 `_variant_t` 개체로 복사할 `_variant_t` 개체입니다.  
  
 `fCopy`  
 false인 경우 제공된 **VARIANT** 개체는 **VariantCopy**로 새 복사본을 만들지 않고 새 `_variant_t` 개체에 연결됩니다.  
  
 *ISrc, sSrc*  
 새 `_variant_t` 개체로 복사할 정수 값입니다.  
  
 `vtSrc`  
 새 `_variant_t` 개체의 **VARTYPE**입니다.  
  
 *fltSrc, dblSrc*  
 새 `_variant_t` 개체에 복사될 숫자 값입니다.  
  
 `cySrc`  
 새 `_variant_t` 개체로 복사할 **CY** 개체입니다.  
  
 `bstrSrc`  
 새 `_bstr_t` 개체로 복사할 `_variant_t` 개체입니다.  
  
 *strSrc, wstrSrc*  
 새 `_variant_t` 개체로 복사할 문자열입니다.  
  
 `bSrc`  
 새 `_variant_t` 개체로 복사할 `bool` 값입니다.  
  
 `pIUknownSrc`  
 새 `_variant_t` 개체로 캡슐화될 **VT\_UNKNOWN** 개체에 대한 COM 인터페이스 포인터입니다.  
  
 `pDispSrc`  
 새 `_variant_t` 개체로 캡슐화될 **VT\_DISPATCH** 개체에 대한 COM 인터페이스 포인터입니다.  
  
 `decSrc`  
 새 `_variant_t` 개체로 복사할 **DECIMAL** 값입니다.  
  
 `bSrc`  
 새 `_variant_t` 개체로 복사할 **BYTE** 값입니다.  
  
 `cSrc`  
 새 `_variant_t` 개체로 복사할 `char` 값입니다.  
  
 *usSrc*  
 새 `_variant_t` 개체로 복사할 **unsigned short** 값입니다.  
  
 *ulSrc*  
 새 `_variant_t` 개체로 복사할 `unsigned long` 값입니다.  
  
 `iSrc`  
 새 `_variant_t` 개체로 복사할 `int` 값입니다.  
  
 *uiSrc*  
 새 `_variant_t` 개체로 복사할 `unsigned int` 값입니다.  
  
 *i8Src*  
 새 `_variant_t` 개체로 복사할 \_\_**int64** 값입니다.  
  
 *ui8Src*  
 새 `_variant_t` 개체로 복사할 **unsigned \_\_int64** 값입니다.  
  
## 설명  
  
-   **\_variant\_t\( \)** 빈 `_variant_t` 개체, `VT_EMPTY`를 생성합니다.  
  
-   **\_variant\_t\( VARIANT&**  *varSrc*  **\) VARIANT** 개체의 복사본에서 `_variant_t` 개체를 생성합니다.  변형 형식이 유지됩니다.  
  
-   **\_variant\_t\( VARIANT\***  *pVarSrc*  **\) VARIANT** 개체의 복사본에서 `_variant_t` 개체를 생성합니다.  변형 형식이 유지됩니다.  
  
-   **\_variant\_t\( \_variant\_t&**  *var\_t\_Src*  **\)** 또 다른 `_variant_t` 개체에서 `_variant_t` 개체를 생성합니다.  변형 형식이 유지됩니다.  
  
-   **\_variant\_t\( VARIANT&**  *varSrc* **, bool**  `fCopy`  **\)** 기존 **VARIANT** 개체에서 `_variant_t` 개체를 생성합니다.  `fCopy`가 **false**인 경우 복사본을 만들지 않고 **VARIANT** 개체가 새 개체에 연결됩니다.  
  
-   **\_variant\_t\( short**  *sSrc* **, VARTYPE**  `vtSrc`  **\= VT\_I2 \) short** 정수 값에서 형식 `VT_I2` 또는 `VT_BOOL`의 `_variant_t` 개체를 생성합니다.  다른 모든 **VARTYPE**은 `E_INVALIDARG` 오류를 발생시킵니다.  
  
-   **\_variant\_t\( long**  `lSrc` **, VARTYPE**  `vtSrc`  **\= VT\_I4 \) long** 정수 값에서 형식 `VT_I4`, `VT_BOOL` 또는 `VT_ERROR`의 `_variant_t` 개체를 생성합니다.  다른 모든 **VARTYPE**은 `E_INVALIDARG` 오류를 발생시킵니다.  
  
-   **\_variant\_t\( float**  `fltSrc`  **\) float** 숫자 값에서 `VT_R4` 형식의 `_variant_t` 개체를 생성합니다.  
  
-   **\_variant\_t\( double**  `dblSrc` **, VARTYPE**  `vtSrc`  **\= VT\_R8 \) double** 숫자 값에서 형식 `VT_R8` 또는 `VT_DATE`의 `_variant_t` 개체를 생성합니다.  다른 모든 **VARTYPE**은 `E_INVALIDARG` 오류를 발생시킵니다.  
  
-   **\_variant\_t\( CY&**  `cySrc`  **\) CY** 개체에서 `VT_CY` 형식의 `_variant_t` 개체를 생성합니다.  
  
-   **\_variant\_t\( \_bstr\_t&**  `bstrSrc`  **\)** `_bstr_t` 개체에서 `VT_BSTR` 형식의 `_variant_t` 개체를 생성합니다.  새 `BSTR`이 할당됩니다.  
  
-   **\_variant\_t\( wchar\_t \*** *wstrSrc*  **\)** 유니코드 문자열에서 `VT_BSTR` 형식의 `_variant_t` 개체를 생성합니다.  새 `BSTR`이 할당됩니다.  
  
-   **\_variant\_t\( char\***  `strSrc`  **\)** 문자열에서 `VT_BSTR` 형식의 `_variant_t` 개체를 생성합니다.  새 `BSTR`이 할당됩니다.  
  
-   **\_variant\_t\( bool**  `bSrc`  **\)** `bool` 값에서 `VT_BOOL` 형식의 `_variant_t` 개체를 생성합니다.  
  
-   **\_variant\_t\( IUnknown\***  `pIUknownSrc` **, bool**  `fAddRef`  **\= true \)** COM 인터페이스 포인터에서 형식 **VT\_UNKNOWN**의 `_variant_t` 개체를 생성합니다.  `fAddRef`가 **true**인 경우 제공된 인터페이스 포인터에 `AddRef`가 호출되어 `_variant_t` 개체가 제거될 때 발생하는 **Release**에 대한 호출에 일치시킵니다.  제공된 인터페이스 포인터에서 **릴리스**를 호출해야 합니다.  `fAddRef`가 **false**인 경우 이 생성자는 제공된 인터페이스 포인터를 소유합니다. 제공된 인터페이스 포인터에서 **릴리스**를 호출하지 마십시오.  
  
-   **\_variant\_t\( IDispatch\***  `pDispSrc` **, bool**  `fAddRef`  **\= true \)** COM 인터페이스 포인터에서 형식 **VT\_DISPATCH**의 `_variant_t` 개체를 생성합니다.  `fAddRef`가 **true**인 경우 제공된 인터페이스 포인터에 `AddRef`가 호출되어 `_variant_t` 개체가 제거될 때 발생하는 **Release**에 대한 호출에 일치시킵니다.  제공된 인터페이스 포인터에서 **릴리스**를 호출해야 합니다.  **fAddRef**가 false인 경우 이 생성자는 제공된 인터페이스 포인터를 소유합니다. 제공된 인터페이스 포인터에서 **릴리스**를 호출하지 마십시오.  
  
-   **\_variant\_t\( DECIMAL&**  `decSrc`  **\) DECIMAL** 값에서 **VT\_DECIMAL** 형식의 `_variant_t` 개체를 생성합니다.  
  
-   **\_variant\_t\( BYTE**  `bSrc`  **\) BYTE**에서 `VT_UI1` 형식의 `_variant_t` 개체를 생성합니다.  
  
 **Microsoft 전용 종료**  
  
## 참고 항목  
 [\_variant\_t 클래스](../cpp/variant-t-class.md)