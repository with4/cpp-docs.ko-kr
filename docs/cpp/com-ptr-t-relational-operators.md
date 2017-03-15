---
title: "_com_ptr_t 관계형 연산자 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_com_ptr_t::operator>"
  - "_com_ptr_t::operator>="
  - "_com_ptr_t.operator<="
  - "_com_ptr_t.operator!="
  - "_com_ptr_t::operator<="
  - "_com_ptr_t.operator>"
  - "_com_ptr_t.operator<"
  - "_com_ptr_t.operator=="
  - "_com_ptr_t::operator=="
  - "_com_ptr_t.operator>="
  - "_com_ptr_t::operator!="
  - "_com_ptr_t::operator<"
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
  - "operator <, 포인터"
  - "operator <=, 포인터"
  - "operator ==, 포인터"
  - "operator >, 포인터"
  - "operator >=, 포인터"
  - "operator!=, 관계형 연산자"
  - "operator<, 포인터"
  - "operator<=, 포인터"
  - "operator==, 포인터"
  - "operator>=, 포인터"
  - "관계형 연산자, _com_ptr_t 클래스"
ms.assetid: 5ae4028c-33ee-485d-bbda-88d2604d6d4b
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# _com_ptr_t 관계형 연산자
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 스마트 포인터 개체를 다른 스마트 포인터, 원시 인터페이스 포인터 또는 **NULL**과 비교합니다.  
  
## 구문  
  
```  
  
      template<typename _OtherIID>   
bool operator==(   
   const _com_ptr_t<_OtherIID>& p   
);  
  
template<typename _OtherIID>    
bool operator==(   
   _com_ptr_t<_OtherIID>& p   
);  
  
template<typename _InterfaceType>   
bool operator==(   
   _InterfaceType* p   
);  
  
template<>   
bool operator==(   
   Interface* p   
);  
  
template<>   
bool operator==(   
   const _com_ptr_t& p   
) throw();  
  
template<>   
bool operator==(   
   _com_ptr_t& p   
) throw();  
  
bool operator==(   
   int null   
);  
```  
  
```  
  
      template<typename _OtherIID>   
bool operator!=(   
   const _com_ptr_t<_OtherIID>& p   
);  
  
template<typename _OtherIID>   
bool operator!=(   
   _com_ptr_t<_OtherIID>& p   
);  
  
template<typename _InterfaceType>   
bool operator!=(   
   _InterfaceType* p   
);  
  
bool operator!=(   
   int null   
);  
```  
  
```  
  
      template<typename _OtherIID>   
bool operator<(   
   const _com_ptr_t<_OtherIID>& p   
);  
  
template<typename _OtherIID>   
bool operator<(   
   _com_ptr_t<_OtherIID>& p   
);  
  
template<typename _InterfaceType>   
bool operator<(   
   _InterfaceType* p   
);  
```  
  
```  
  
      template<typename _OtherIID>   
bool operator>(   
   const _com_ptr_t<_OtherIID>& p   
);  
  
template<typename _OtherIID>   
bool operator>(_com_ptr_t<   
   _OtherIID>& p   
);  
  
template<typename _InterfaceType>   
bool operator>(   
   _InterfaceType* p   
);  
```  
  
```  
  
      template<typename _OtherIID>   
bool operator<=(   
   const _com_ptr_t<_OtherIID>& p   
);  
  
template<typename _OtherIID>   
bool operator<=(   
   _com_ptr_t<_OtherIID>& p   
);  
  
template<typename _InterfaceType>   
bool operator<=(   
   _InterfaceType* p   
);  
```  
  
```  
  
      template<typename _OtherIID>   
bool operator>=(   
   const _com_ptr_t<_OtherIID>& p   
);  
  
template<typename _OtherIID>   
bool operator>=(   
   _com_ptr_t<_OtherIID>& p   
);  
  
template<typename _InterfaceType>   
bool operator>=(   
   _InterfaceType* p   
);  
```  
  
## 설명  
 스마트 포인터 개체를 다른 스마트 포인터, 원시 인터페이스 포인터 또는 **NULL**과 비교합니다.  **NULL** 포인터 테스트를 제외하고 이러한 연산자는 먼저 두 포인터에 **IUnknown**을 쿼리하고 그 결과를 비교합니다.  
  
 **Microsoft 전용 종료**  
  
## 참고 항목  
 [\_com\_ptr\_t 클래스](../cpp/com-ptr-t-class.md)