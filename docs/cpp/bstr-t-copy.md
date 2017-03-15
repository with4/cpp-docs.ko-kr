---
title: "_bstr_t::copy | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_bstr_t::copy"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BSTR 개체, copy"
  - "Copy 메서드"
ms.assetid: 00ba7311-e82e-4a79-8106-5329fa2f869a
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# _bstr_t::copy
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 캡슐화된 `BSTR`의 복사본을 구성합니다.  
  
## 구문  
  
```  
  
      BSTR copy(  
  bool fCopy = true  
) const;  
```  
  
#### 매개 변수  
 `fCopy`  
 **true**인 경우 **copy**는 포함된 `BSTR`의 복사본을 반환하고, 그렇지 않으면 **copy**는 실제 BSTR을 반환합니다.  
  
## 설명  
 캡슐화된 `BSTR` 개체에 새로 할당된 복사본을 반환합니다.  
  
## 예제  
  
```  
STDMETHODIMP CAlertMsg::get_ConnectionStr(BSTR *pVal){ //  m_bsConStr is _bstr_t  
   *pVal = m_bsConStr.copy();  
}  
```  
  
 **Microsoft 전용 종료**  
  
## 참고 항목  
 [\_bstr\_t 클래스](../cpp/bstr-t-class.md)