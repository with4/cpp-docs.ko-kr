---
title: "_com_ptr_t::QueryInterface | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_com_ptr_t::QueryInterface"
  - "_com_ptr_t.QueryInterface"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "QueryInterface 메서드"
ms.assetid: d03292f1-6b02-40db-9756-8b0837a97319
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# _com_ptr_t::QueryInterface
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 캡슐화된 인터페이스 포인터에 **IUnknown**의 멤버 함수 `QueryInterface`를 호출합니다.  
  
## 구문  
  
```  
  
      template<typename _InterfaceType> HRESULT QueryInterface (  
   const IID& iid,  
   _InterfaceType*& p   
) throw ( );  
template<typename _InterfaceType> HRESULT QueryInterface (  
   const IID& iid,  
   _InterfaceType** p  
) throw( );  
```  
  
#### 매개 변수  
 `iid`  
 인터페이스 포인터의 **IID**입니다.  
  
 `p`  
 원시 인터페이스 포인터입니다.  
  
## 설명  
 지정된 **IID**가 있는 캡슐화된 인터페이스 포인터에 대해 **IUnknown::QueryInterface**를 호출하고, `p`에서 그 결과로 생성된 원시 인터페이스 포인터를 반환합니다.  이 루틴은 `HRESULT`를 반환하여 성공 또는 실패를 나타냅니다.  
  
 **Microsoft 전용 종료**  
  
## 참고 항목  
 [\_com\_ptr\_t 클래스](../cpp/com-ptr-t-class.md)