---
title: "CComObjectGlobal Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CComObjectGlobal"
  - "ATL::CComObjectGlobal<Base>"
  - "ATL::CComObjectGlobal"
  - "ATL.CComObjectGlobal"
  - "ATL.CComObjectGlobal<Base>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComObjectGlobal class"
ms.assetid: 79bdee55-66e4-4536-b5b3-bdf09f78b9a6
caps.latest.revision: 19
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CComObjectGlobal Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스를 포함 하는 모듈의 참조 횟수 관리를 `Base` 개체입니다.  
  
## 구문  
  
```  
  
      template<  
   class Base   
>  
class CComObjectGlobal :  
   public Base  
```  
  
#### 매개 변수  
 `Base`  
 파생 클래스에서  [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) 또는  [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), 개체에서 지 원하는 다른 인터페이스 이름으로 원하는 대로.  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CComObjectGlobal::CComObjectGlobal](../Topic/CComObjectGlobal::CComObjectGlobal.md)|생성자입니다.|  
|[CComObjectGlobal::~CComObjectGlobal](../Topic/CComObjectGlobal::~CComObjectGlobal.md)|소멸자|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CComObjectGlobal::AddRef](../Topic/CComObjectGlobal::AddRef.md)|전역 구현 `AddRef`.|  
|[CComObjectGlobal::QueryInterface](../Topic/CComObjectGlobal::QueryInterface.md)|전역 구현 `QueryInterface`.|  
|[CComObjectGlobal::Release](../Topic/CComObjectGlobal::Release.md)|전역 구현  **릴리스**.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CComObjectGlobal::m\_hResFinalConstruct](../Topic/CComObjectGlobal::m_hResFinalConstruct.md)|포함의  **HRESULT** 생성 하는 동안 반환 된 `CComObjectGlobal` 개체.|  
  
## 설명  
 `CComObjectGlobal`포함 하는 모듈의 참조 횟수를 관리를 `Base` 개체입니다.  `CComObjectGlobal`모듈을 해제 하는 경우 개체는 삭제 되지 않습니다 보장 합니다.  전체 모듈의 참조 횟수가 0이 되 면 개체는 제거 됩니다.  
  
 예를 들어, 사용 하 여 `CComObjectGlobal`, 모든 클라이언트에서 공유 하는 일반적인 전역 개체 클래스 팩터리를 보유할 수 있습니다.  
  
## 상속 계층 구조  
 `Base`  
  
 `CComObjectGlobal`  
  
## 요구 사항  
 **헤더:**  atlcom.h  
  
## 참고 항목  
 [CComObjectStack Class](../../atl/reference/ccomobjectstack-class.md)   
 [CComAggObject Class](../../atl/reference/ccomaggobject-class.md)   
 [CComObject Class](../../atl/reference/ccomobject-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)