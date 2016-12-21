---
title: "CComCachedTearOffObject Class | Microsoft Docs"
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
  - "ATL::CComCachedTearOffObject"
  - "ATL.CComCachedTearOffObject"
  - "ATL.CComCachedTearOffObject<contained>"
  - "CComCachedTearOffObject"
  - "ATL::CComCachedTearOffObject<contained>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "캐시, ATL cached tear-off objects"
  - "CComCachedTearOffObject class"
ms.assetid: ae19507d-a1de-4dbc-a988-da9f75a50c95
caps.latest.revision: 19
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CComCachedTearOffObject Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 구현  [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) 분리 된 인터페이스.  
  
## 구문  
  
```  
  
      template <  
   class contained  
>  
class CComCachedTearOffObject : public IUnknown,  
   public CComObjectRootEx< contained::_ThreadModel::ThreadModelNoCS >  
```  
  
#### 매개 변수  
 `contained`  
 분리 된 클래스를 파생 하는에서 `CComTearOffObjectBase` 인터페이스를 지원 하 여 분리 개체 원하는.  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CComCachedTearOffObject::CComCachedTearOffObject](../Topic/CComCachedTearOffObject::CComCachedTearOffObject.md)|생성자입니다.|  
|[CComCachedTearOffObject::~CComCachedTearOffObject](../Topic/CComCachedTearOffObject::~CComCachedTearOffObject.md)|소멸자|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CComCachedTearOffObject::AddRef](../Topic/CComCachedTearOffObject::AddRef.md)|참조 횟수를 증가 `CComCachedTearOffObject` 개체입니다.|  
|[CComCachedTearOffObject::FinalConstruct](../Topic/CComCachedTearOffObject::FinalConstruct.md)|호출 된 `m_contained::FinalConstruct` \(분리 된 클래스 메서드\).|  
|[CComCachedTearOffObject::FinalRelease](../Topic/CComCachedTearOffObject::FinalRelease.md)|호출 된 `m_contained::FinalRelease` \(분리 된 클래스 메서드\).|  
|[CComCachedTearOffObject::QueryInterface](../Topic/CComCachedTearOffObject::QueryInterface.md)|반환에 대 한 포인터는 `IUnknown` 의 `CComCachedTearOffObject` 개체를 분리 된 클래스에 있는 요청 된 인터페이스 \(클래스 `contained`\).|  
|[CComCachedTearOffObject::Release](../Topic/CComCachedTearOffObject::Release.md)|참조 횟수를 감소는 `CComCachedTearOffObject` 및 개체의 참조 횟수가 0 이면 삭제 합니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CComCachedTearOffObject::m\_contained](../Topic/CComCachedTearOffObject::m_contained.md)|A `CComContainedObject` 파생 클래스에서 분리 된 개체 \(클래스의 `contained`\).|  
  
## 설명  
 `CComCachedTearOffObject`구현  [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) 분리 된 인터페이스.  이 클래스에서 다른 `CComTearOffObject` 는 `CComCachedTearOffObject` 는 자체의  **IUnknown**별도의 소유자가 개체의  **IUnknown** \(에 절취 만들어질 개체 소유자입니다\).  `CComCachedTearOffObject`자체 유지 참조 개수에 해당  **IUnknown** 참조 계수가 0이 되 면 자체를 삭제 합니다.  그러나 해당 떼어가기 중 하나에 대해 쿼리 하는 경우 인터페이스, 소유자 개체의 참조 횟수를  **IUnknown** 증가 합니다.  
  
 경우는 `CComCachedTearOffObject` 개체는 분리 된 구현 되어 이미 인스턴스화할 및 분리 된 인터페이스를 다시 동일한 쿼리 `CComCachedTearOffObject` 개체를 다시 사용 합니다.  대비에 의해 분리 된 인터페이스를 구현 하는 경우에 `CComTearOffObject` 소유자 개체를 통해 다시에 대 한 쿼리 다른 `CComTearOffObject` 인스턴스화할 수 있습니다.  
  
 소유자 클래스에 구현 해야 `FinalRelease` 호출 하 고  **릴리스** 에 캐시 된  **IUnknown** 에 `CComCachedTearOffObject`는 해당 참조 횟수가 감소 됩니다.  그러면 `CComCachedTearOffObject`의 `FinalRelease` 호출의 분리 된 삭제 하.  
  
## 상속 계층 구조  
 `CComObjectRootBase`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `IUnknown`  
  
 `CComCachedTearOffObject`  
  
## 요구 사항  
 **헤더:**  atlcom.h  
  
## 참고 항목  
 [CComTearOffObject Class](../../atl/reference/ccomtearoffobject-class.md)   
 [CComObjectRootEx Class](../../atl/reference/ccomobjectrootex-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)