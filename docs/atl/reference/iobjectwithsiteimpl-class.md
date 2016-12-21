---
title: "IObjectWithSiteImpl Class | Microsoft Docs"
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
  - "ATL::IObjectWithSiteImpl"
  - "ATL.IObjectWithSiteImpl<T>"
  - "IObjectWithSiteImpl"
  - "ATL.IObjectWithSiteImpl"
  - "ATL::IObjectWithSiteImpl<T>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IObjectWithSiteImpl class"
ms.assetid: 4e1f774f-bc3d-45ee-9a1c-c3533a511588
caps.latest.revision: 18
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IObjectWithSiteImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스 개체의 사이트와 통신할 수 있도록 하는 메서드를 제공 합니다.  
  
## 구문  
  
```  
  
      template<  
   class T   
>  
class ATL_NO_VTABLE IObjectWithSiteImpl :  
   public IObjectWithSite  
```  
  
#### 매개 변수  
 `T`  
 파생 클래스에서 `IObjectWithSiteImpl`.  
  
## Members  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[IObjectWithSiteImpl::GetSite](../Topic/IObjectWithSiteImpl::GetSite.md)|사이트에 대 한 인터페이스 포인터를 쿼리합니다.|  
|[IObjectWithSiteImpl::SetChildSite](../Topic/IObjectWithSiteImpl::SetChildSite.md)|사이트의 개체를 제공 합니다.  **IUnknown**  포인터.|  
|[IObjectWithSiteImpl::SetSite](../Topic/IObjectWithSiteImpl::SetSite.md)|사이트의 개체를 제공 합니다.  **IUnknown** 포인터.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[IObjectWithSiteImpl::m\_spUnkSite](../Topic/IObjectWithSiteImpl::m_spUnkSite.md)|관리 사이트의  **IUnknown** 포인터.|  
  
## 설명  
 [IObjectWithSite](http://msdn.microsoft.com/library/windows/desktop/ms693765) 인터페이스 개체의 사이트와 통신할 수 있습니다.  클래스 `IObjectWithSiteImpl` 는이 인터페이스의 기본 구현을 제공 하 고 구현  **IUnknown** 덤프에 정보를 전송 하 여 장치에서 디버그 빌드.  
  
 `IObjectWithSiteImpl`두 메서드를 지정합니다.  첫 번째 호출은 클라이언트 `SetSite`를 전달 하는 사이트  **IUnknown** 포인터.  이 포인터가 개체 내에 저장 되 고 나중에 호출을 통해 검색할 수 있습니다 `GetSite`.  
  
 클래스에서 파생 하는 일반적으로 `IObjectWithSiteImpl` 때 개체는 만들고 있는 컨트롤입니다.  컨트롤의 클래스에서 파생  [IOleObjectImpl](../../atl/reference/ioleobjectimpl-class.md), 사이트 포인터도 제공 합니다.  클래스를 파생 하지 `IObjectWithSiteImpl` 및 `IOleObjectImpl`.  
  
## 상속 계층 구조  
 `IObjectWithSite`  
  
 `IObjectWithSiteImpl`  
  
## 요구 사항  
 **헤더:**  atlcom.h  
  
## 참고 항목  
 [Class Overview](../../atl/atl-class-overview.md)