---
title: "_bstr_t::wchar_t*, _bstr_t::char* | Microsoft Docs"
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
  - "_bstr_t::wchar_t*"
  - "_bstr_t::char*"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "operator char*"
  - "operator wchar_t*"
ms.assetid: acd9f4a7-b427-42c2-aaae-acae21cab317
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _bstr_t::wchar_t*, _bstr_t::char*
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 BSTR 문자는 좁거나 넓은 문자 배열로 반환됩니다.  
  
## 구문  
  
```  
  
      operator const wchar_t*( ) const throw( );   
operator wchar_t*( ) const throw( );   
operator const char*( ) const;   
operator char*( ) const;  
```  
  
## 설명  
 이러한 연산자는 `BSTR` 개체로 캡슐화된 문자 데이터를 추출하는 데 사용될 수 있습니다.  반환된 포인터에 새 값을 할당하면 원래 BSTR 데이터는 수정되지 않습니다.  
  
 **Microsoft 전용 종료**  
  
## 참고 항목  
 [\_bstr\_t 클래스](../cpp/bstr-t-class.md)