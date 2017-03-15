---
title: "_variant_t Extractors | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_variant_t.operatordouble"
  - "operatorlong"
  - "_variant_t::operator_bstr_t"
  - "operatordouble"
  - "_variant_t.operatorCY"
  - "operatorCY"
  - "_variant_t::operatorCY"
  - "_variant_t::operatordouble"
  - "operatorfloat"
  - "operatorBYTE"
  - "_variant_t.operatorDECIMAL"
  - "_variant_t::operatorlong"
  - "operatorIDispatch"
  - "_variant_t.operatorBYTE"
  - "operatorDECIMAL"
  - "_variant_t.operator_bstr_t"
  - "_variant_t::operatorDECIMAL"
  - "_variant_t.operatorIUnknown"
  - "_variant_t.operatorlong"
  - "_variant_t::operatorIDispatch"
  - "_variant_t::operatorIUnknown"
  - "operatorIUnknown"
  - "_variant_t.operatorbool"
  - "_variant_t::operatorBYTE"
  - "_variant_t.operatorfloat"
  - "operator_bstr_t"
  - "_variant_t::operatorbool"
  - "operatorshort"
  - "_variant_t::operatorshort"
  - "_variant_t::operatorfloat"
  - "_variant_t.operatorIDispatch"
  - "_variant_t.operatorshort"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "추출기, _variant_t 클래스"
  - "operator _bstr_t"
  - "operator bool"
  - "operator BYTE"
  - "operator CY"
  - "operator DECIMAL"
  - "operator double"
  - "operator float"
  - "operator IDispatch"
  - "operator IUnknown"
  - "operator long"
  - "operator SHORT"
ms.assetid: 33c1782f-045a-4673-9619-1d750efc83a9
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# _variant_t Extractors
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 캡슐화된 **VARIANT** 개체에서 데이터를 추출합니다.  
  
## 구문  
  
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
  
## 설명  
 캡슐화된 **VARIANT**에서 원시 데이터를 추출합니다.  **VARIANT**가 이미 올바른 형식이 아닌 경우 변환을 시도하기 위해 **VariantChangeType**가 사용되며 실패 시 오류가 발생합니다.  
  
-   **연산자 short\( \) short** 정수 값을 추출합니다.  
  
-   **연산자 long\( \) long** 정수 값을 추출합니다.  
  
-   **연산자 float\( \) float** 숫자 값을 추출합니다.  
  
-   **연산자 double\( \) 이중** 정수 값을 추출합니다.  
  
-   **연산자 CY\( \) CY** 개체를 추출합니다.  
  
-   **연산자 bool\( \)** `bool` 값을 추출합니다.  
  
-   **연산자 DECIMAL\( \) DECIMAL** 값을 추출합니다.  
  
-   **연산자 BYTE\( \) BYTE** 값을 추출합니다.  
  
-   **연산자 \_bstr\_t\( \)** `_bstr_t` 개체에서 캡슐화된 문자열을 추출합니다.  
  
-   **연산자 IDispatch \*\( \)** 캡슐화된 **VARIANT**에서 dispinterface 포인터를 추출합니다.  `AddRef`는 결과 포인터에서 호출되므로 **Release**를 호출하여 해제할 수 있습니다.  
  
-   **연산자 IUnknown\*\( \)** 캡슐화된 **VARIANT**에서 COM 인터페이스 포인터를 추출합니다.  `AddRef`는 결과 포인터에서 호출되므로 **Release**를 호출하여 해제할 수 있습니다.  
  
 **Microsoft 전용 종료**  
  
## 참고 항목  
 [\_variant\_t 클래스](../cpp/variant-t-class.md)