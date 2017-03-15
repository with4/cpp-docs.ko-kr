---
title: "_variant_t::operator = | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_variant_t.operator="
  - "_variant_t::operator="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "= 연산자, 특정 Visual C++ 개체와 사용"
  - "operator =, variant"
  - "operator=, variant"
ms.assetid: 77622723-6e49-4dec-9e0f-fa74028f1a3c
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _variant_t::operator =
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
## 구문  
  
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
  
## 설명  
 다음 연산자는 `_variant_t` 개체에 새 값을 할당합니다.  
  
-   **operator\=\(**  *varSrc*  **\)** `_variant_t` 개체에 기존 **VARIANT**를 할당합니다.  
  
-   **operator\=\(**  *pVarSrc*  **\)** `_variant_t` 개체에 기존 **VARIANT**를 할당합니다.  
  
-   **operator\=\(**  *var\_t\_Src*  **\)** `_variant_t` 개체에 기존 `_variant_t` 개체를 할당합니다.  
  
-   **operator\=\(**  *sSrc*  **\)** `_variant_t` 개체에 **short** 정수 값을 할당합니다.  
  
-   **operator\=\(**  `lSrc`  **\)** `_variant_t` 개체에 **long** 정수 값을 할당합니다.  
  
-   **operator\=\(**  *fltSrc*  **\)** `_variant_t` 개체에 **float** 숫자 값을 할당합니다.  
  
-   **operator\=\(**  *dblSrc*  **\)** `_variant_t` 개체에 **double** 숫자 값을 할당합니다.  
  
-   **operator\=\(**  *cySrc*  **\)** `_variant_t` 개체에 **CY** 개체를 할당합니다.  
  
-   **operator\=\(**  *bstrSrc*  **\)** `_variant_t` 개체에 `BSTR` 개체를 할당합니다.  
  
-   **operator\=\(**  *wstrSrc*  **\)** `_variant_t` 개체에 유니코드 문자열을 할당합니다.  
  
-   **operator\=\(**  `strSrc`  **\)** `_variant_t` 개체에 멀티바이트 문자열을 할당합니다.  
  
-   **operator\=\(**  `bSrc` **\)** `_variant_t` 개체에 `bool` 값을 할당합니다.  
  
-   **operator\=\(**  *pDispSrc*  **\)** `_variant_t` 개체에 **VT\_DISPATCH** 개체를 할당합니다.  
  
-   **operator\=\(**  *pIUnknownSrc*  **\)** `_variant_t` 개체에 **VT\_UNKNOWN** 개체를 할당합니다.  
  
-   **operator\=\(**  *decSrc*  **\)** `_variant_t` 개체에 **DECIMAL** 값을 할당합니다.  
  
-   **operator\=\(**  `bSrc` **\)** `_variant_t` 개체에 **BYTE** 값을 할당합니다.  
  
 **Microsoft 전용 종료**  
  
## 참고 항목  
 [\_variant\_t 클래스](../cpp/variant-t-class.md)