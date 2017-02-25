---
title: "알림 수신 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "이벤트[C++], OLE DB에서 알림"
  - "알림[C++], 이벤트"
  - "알림[C++], OLE DB 소비자"
  - "OLE DB 소비자, 알림"
  - "OLE DB 공급자, 알림"
  - "OLE DB의 알림 메시지 받기"
  - "행 집합, 이벤트 알림"
ms.assetid: 305a1103-0c87-40c8-94bc-7fbbdd52ae32
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# 알림 수신
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OLE DB는 이벤트가 발생할 경우 알림을 수신하기 위한 인터페이스를 제공합니다.  자세한 내용은 *OLE DB Programmer's Reference*에서 [OLE DB Object Notifications](https://msdn.microsoft.com/en-us/library/ms725406.aspx)을 참조하십시오.  이러한 이벤트의 설정은 표준 COM 연결 포인트 메커니즘을 사용합니다.  예를 들어, `IRowsetNotify`를 통해 이벤트를 검색하는 ATL 개체는 클래스 파생 목록에 `IRowsetNotify`를 추가하고 **COM\_INTERFACE\_ENTRY** 매크로를 통해 이를 노출하여 `IRowsetNotify` 인터페이스를 구현합니다.  
  
 `IRowsetNotify`에는 세 가지 메서드가 있으며, 이들은 다양한 경우에 호출될 수 있습니다.  이들 메서드 중 하나에만 응답하려는 경우, 응답하지 않을 메서드에 대해 **E\_NOTIMPL**을 반환하는 [IRowsetNotifyImpl](../../data/oledb/irowsetnotifyimpl-class.md) 클래스를 사용할 수 있습니다.  
  
 행 집합을 만들 경우, 알림 설정에 필요한 **IConnectionPointContainer**를 지원하는 반환된 행 집합 개체가 필요하다는 점을 공급자에게 알려야 합니다.  
  
 다음 코드에서는 ATL 개체에서 행 집합을 열고 `AtlAdvise` 함수를 사용하여 알림 싱크를 설정하는 방법을 보여 줍니다.  `AtlAdvise`는 `AtlUnadvise`를 호출할 때 사용되는 쿠키를 반환합니다.  
  
```  
CDBPropSet propset(DBPROPSET_ROWSET);  
propset.AddProperty(DBPROP_IConnectionPointContainer, true);  
  
product.Open(session, _T("Products"), &propset);  
  
AtlAdvise(product.m_spRowset, GetUnknown(), IID_IRowsetNotify, &m_dwCookie);  
```  
  
## 참고 항목  
 [접근자 사용](../../data/oledb/using-accessors.md)