---
title: "_bstr_t 관계형 연산자 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_bstr_t::operator>"
  - "_bstr_t::operator=="
  - "_bstr_t::operator>="
  - "_bstr_t::operator!="
  - "_bstr_t::operator<"
  - "_bstr_t::operator<="
  - "_bstr_t::operator!"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "!= 연산자"
  - "< 연산자, 특정 개체 비교"
  - "<= 연산자, 특정 개체와 사용"
  - "== 연산자, 특정 Visual C++ 개체와 사용"
  - "> 연산자, 특정 개체 비교"
  - ">= 연산자, 특정 개체 비교"
  - "operator !=, 관계형 연산자"
  - "operator <, bstr"
  - "operator <=, bstr"
  - "operator ==, bstr"
  - "operator >, bstr"
  - "operator >=, bstr"
  - "operator!=, 관계형 연산자"
  - "operator<, bstr"
  - "operator<=, bstr"
  - "operator==, bstr"
  - "operator>=, bstr"
  - "관계형 연산자, _bstr_t 클래스"
ms.assetid: e153da72-37c3-4d8a-b8eb-730d65da64dd
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# _bstr_t 관계형 연산자
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 두 `_bstr_t` 개체를 비교합니다.  
  
## 구문  
  
```  
  
      bool operator!( ) const throw( );   
bool operator==(  
   const _bstr_t& str   
) const throw( );  
bool operator!=(  
   const _bstr_t& str   
) const throw( );  
bool operator<(  
   const _bstr_t& str   
) const throw( );  
bool operator>(  
   const _bstr_t& str   
) const throw( );  
bool operator<=(  
   const _bstr_t& str   
) const throw( );  
bool operator>=(  
   const _bstr_t& str   
) const throw( );  
```  
  
## 설명  
 이러한 연산자는 두 `_bstr_t` 개체를 사전순으로 비교합니다.  연산자는 비교가 유효하면 **true**를 반환하고, 그렇지 않으면 **false**를 반환합니다.  
  
 **Microsoft 전용 종료**  
  
## 참고 항목  
 [\_bstr\_t 클래스](../cpp/bstr-t-class.md)