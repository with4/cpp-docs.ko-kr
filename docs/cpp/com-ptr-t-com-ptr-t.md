---
title: "_com_ptr_t::_com_ptr_t | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_com_ptr_t::_com_ptr_t"
  - "_com_ptr_t._com_ptr_t"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_com_ptr_t 메서드"
ms.assetid: 0c00620a-28d2-4f60-ae4a-1696be36137e
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# _com_ptr_t::_com_ptr_t
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 `_com_ptr_t` 개체를 생성합니다.  
  
## 구문  
  
```  
// Default constructor.  
// Constructs a NULL smart pointer.  
_com_ptr_t() throw();  
  
// Constructs a NULL smart pointer. The NULL argument must be zero.  
_com_ptr_t(   
   int null   
);  
  
// Constructs a smart pointer as a copy of another instance of the   
// same smart pointer. AddRef is called to increment the reference   
// count for the encapsulated interface pointer.  
_com_ptr_t(   
   const _com_ptr_t& cp   
) throw();  
  
// Constructs a smart pointer from a raw interface pointer of this   
// smart pointer's type. If fAddRef is true, AddRef is called   
// to increment the reference count for the encapsulated   
// interface pointer. If fAddRef is false, this constructor   
// takes ownership of the raw interface pointer without calling AddRef.  
_com_ptr_t(   
   Interface* pInterface,   
   bool fAddRef   
) throw();  
  
// Construct pointer for a _variant_t object.  
// Constructs a smart pointer from a _variant_t object. The   
// encapsulated VARIANT must be of type VT_DISPATCH or VT_UNKNOWN, or   
// it can be converted into one of these two types. If QueryInterface   
// fails with an E_NOINTERFACE error, a NULL smart pointer is   
// constructed.  
_com_ptr_t(   
   const _variant_t& varSrc   
);  
  
// Constructs a smart pointer given the CLSID of a coclass. This   
// function calls CoCreateInstance, by the member function  
//  CreateInstance, to create a new COM object and then queries for   
// this smart pointer's interface type. If QueryInterface fails with   
// an E_NOINTERFACE error, a NULL smart pointer is constructed.  
explicit _com_ptr_t(   
   const CLSID& clsid,    
   IUnknown* pOuter = NULL,    
   DWORD dwClsContext = CLSCTX_ALL   
);  
  
// Calls CoCreateClass with provided CLSID retrieved from string.  
explicit _com_ptr_t(   
   LPCWSTR str,    
   IUnknown* pOuter = NULL,    
   DWORD dwClsContext = CLSCTX_ALL   
);  
  
// Constructs a smart pointer given a multibyte character string that   
// holds either a CLSID (starting with "{") or a ProgID. This function   
// calls CoCreateInstance, by the member function CreateInstance, to   
// create a new COM object and then queries for this smart pointer's   
// interface type. If QueryInterface fails with an E_NOINTERFACE error,   
// a NULL smart pointer is constructed.  
explicit _com_ptr_t(   
   LPCSTR str,   
   IUnknown* pOuter = NULL,   
   DWORD dwClsContext = CLSCTX_ALL   
);  
  
// Saves the interface.  
template<>    
_com_ptr_t(   
   Interface* pInterface   
) throw();  
  
// Make sure correct ctor is called  
template<>    
_com_ptr_t(   
   LPSTR str   
);  
  
// Make sure correct ctor is called  
template<>    
_com_ptr_t(   
   LPWSTR str   
);  
  
// Constructs a smart pointer from a different smart pointer type or   
// from a different raw interface pointer. QueryInterface is called to   
// find an interface pointer of this smart pointer's type. If   
// QueryInterface fails with an E_NOINTERFACE error, a NULL smart   
// pointer is constructed.  
template<typename _OtherIID>    
_com_ptr_t(   
   const _com_ptr_t<_OtherIID>& p   
);  
  
// Constructs a smart-pointer from any IUnknown-based interface pointer.  
template<typename _InterfaceType>   
_com_ptr_t(   
   _InterfaceType* p   
);  
  
// Disable conversion using _com_ptr_t* specialization of  
// template<typename _InterfaceType> _com_ptr_t(_InterfaceType* p)  
template<>    
explicit _com_ptr_t(   
   _com_ptr_t* p   
);  
```  
  
#### 매개 변수  
 `pInterface`  
 원시 인터페이스 포인터입니다.  
  
 `fAddRef`  
 **true**인 경우, 캡슐화된 인터페이스 포인터의 참조 횟수를 증가시키는`AddRef`가 호출됩니다.  
  
 *cp*  
 `_com_ptr_t` 개체  
  
 `p`  
 이 `_com_ptr_t` 개체의 스마트 포인터 형식과 다른 형식의 원시 인터페이스 포인터입니다.  
  
 *varSrc*  
 `_variant_t` 개체  
  
 `clsid`  
 coclass의 **CLSID**입니다.  
  
 `dwClsContext`  
 실행 코드를 실행하는 컨텍스트입니다.  
  
 *lpcStr*  
 **CLSID**\("**{**"로 시작\) 또는 **ProgID**를 보유하는 멀티바이트 문자열입니다.  
  
 `pOuter`  
 [집합체](http://msdn.microsoft.com/library/windows/desktop/ms686558)에서 알 수 없는 외부 형식입니다.  
  
## 참고 항목  
 [\_com\_ptr\_t 클래스](../cpp/com-ptr-t-class.md)