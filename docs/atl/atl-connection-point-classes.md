---
title: "ATL Connection Point Classes | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL, 연결 지점"
  - "CComDynamicUnkArray class, connection point classes"
  - "CComUnkArray class, connection point classes"
  - "CFirePropNotifyEvent class"
  - "CFirePropNotifyEvent class, connection point classes"
  - "연결 지점[C++], ATL 클래스"
ms.assetid: 9582ba71-7ace-4df4-9c9b-1b0636953efc
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ATL Connection Point Classes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ATL 다음 클래스를 사용 하 여 연결 지점을 지원 합니다.  
  
-   [IConnectionPointImpl](../atl/reference/iconnectionpointimpl-class.md) 연결 지점을 구현 합니다.  해당 하는 송신 인터페이스의 IID는 템플릿 매개 변수로 전달 됩니다.  
  
-   [IConnectionPointContainerImpl](../atl/reference/iconnectionpointcontainerimpl-class.md) 연결 지점 컨테이너를 구현 하 고 목록을 관리 `IConnectionPointImpl` 개체입니다.  
  
-   [IPropertyNotifySinkCP](../atl/reference/ipropertynotifysinkcp-class.md) 연결 지점을 나타내는 구현 된  [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638) 인터페이스.  
  
-   [CComDynamicUnkArray](../atl/reference/ccomdynamicunkarray-class.md) 는 임의 개수의 연결 지점 및 해당 싱크 간의 연결을 관리 합니다.  
  
-   [CComUnkArray](../atl/reference/ccomunkarray-class.md) 는 미리 정의 된 많은 템플릿 매개 변수에 의해 지정 된 연결을 관리 합니다.  
  
-   [CFirePropNotifyEvent](../atl/reference/cfirepropnotifyevent-class.md) 는 개체의 속성 변경 되었거나 변경 되는 클라이언트 싱크를 알립니다.  
  
-   [IDispEventImpl](../atl/reference/idispeventimpl-class.md) ATL COM 개체에 대 한 연결 지점에 대 한 지원을 제공 합니다.  이러한 연결 지점은 COM 개체가 제공 하는 이벤트 싱크 맵을 함께 매핑됩니다.  
  
-   [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md) 이벤트 싱크 맵을 클래스 경로 이벤트에 적절 한 처리기 함수를 함께 사용 합니다.  
  
## 참고 항목  
 [연결 지점](../atl/atl-connection-points.md)