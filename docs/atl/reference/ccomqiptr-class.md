---
title: "CComQIPtr Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CComQIPtr"
  - "ATL::CComQIPtr"
  - "CComQIPtr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComQIPtr class"
ms.assetid: 969cacb5-05b6-4af4-b683-24911d70242d
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CComQIPtr Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

COM 인터페이스 포인터를 관리 하는 스마트 포인터 클래스입니다.  
  
## 구문  
  
```  
  
      template<  
   class T,  
   const IID* piid = &__uuidof(T)  
>  
class CComQIPtr: public CComPtr<T>  
```  
  
#### 매개 변수  
 `T`  
 저장 되는 포인터 유형을 지정 하는 COM 인터페이스입니다.  
  
 `piid`  
 IID에 대 한 포인터 `T`.  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CComQIPtr::CComQIPtr](../Topic/CComQIPtr::CComQIPtr.md)|생성자입니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[CComQIPtr::operator \=](../Topic/CComQIPtr::operator%20=.md)|포인터 멤버 포인터를 할당합니다.|  
  
## 설명  
 ATL을 사용 하 여 `CComQIPtr` 및  [CComPtr](../../atl/reference/ccomptr-class.md) COM 인터페이스 포인터를 관리 하는 파생  [CComPtrBase](../../atl/reference/ccomptrbase-class.md).  두 클래스 모두 자동 참조 카운팅 호출을 통해 수행 `AddRef` 및  **릴리스**.  오버 로드 된 연산자는 포인터 연산을 처리 합니다.  
  
## 상속 계층 구조  
 [CComPtrBase](../../atl/reference/ccomptrbase-class.md)  
  
 [CComPtr](../../atl/reference/ccomptr-class.md)  
  
 `CComQIPtr`  
  
## 요구 사항  
 **헤더:**  atlcomcli.h  
  
## 참고 항목  
 [CComPtr::CComPtr](../Topic/CComPtr::CComPtr.md)   
 [CComQIPtr::CComQIPtr](../Topic/CComQIPtr::CComQIPtr.md)   
 [CComPtrBase Class](../../atl/reference/ccomptrbase-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [CComQIPtrElementTraits Class](../../atl/reference/ccomqiptrelementtraits-class.md)