---
title: "IRowsetNotifyCP 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IRowsetNotifyCP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IRowsetNotifyCP 클래스"
ms.assetid: ccef402b-94a0-4c2e-9a13-7e854ef82390
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# IRowsetNotifyCP 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implements the provider site for the connection point interface [IRowsetNotify](https://msdn.microsoft.com/en-us/library/ms712959.aspx).  
  
## 구문  
  
```  
template <  
   class T,   
   class ReentrantEventSync = CComSharedMutex   
>  
class IRowsetNotifyCP :   
   public IConnectionPointImpl<  
      T,   
      piid = &__uuidof(IRowsetNotify),   
      CComDynamicUnkArray DynamicUnkArray  
   >,  
   public ReentrantEventSync  
```  
  
#### 매개 변수  
 `T`  
 A class derived from `IRowsetNotifyCP`.  
  
 `ReentrantEventSync`  
 A mutex class that supports reentrancy \(the default is **CComSharedMutex**\).  A mutex is a synchronization object that allows one thread mutually exclusive access to a resource.  
  
 `piid`  
 A interface ID pointer \(**IID\***\) for an **IRowsetNotify** connection point interface.  The default value is **&\_\_uuidof\(IRowsetNotify\)**.  
  
 `DynamicUnkArray`  
 An array of type [CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md), which is a dynamically allocated array of **IUnknown** pointers to the client sink interfaces.  
  
## 멤버  
  
### 메서드  
  
|||  
|-|-|  
|[Fire\_OnFieldChange](../../data/oledb/irowsetnotifycp-fire-onfieldchange.md)|Notifies the consumer of a change to the value of a column.|  
|[Fire\_OnRowChange](../../data/oledb/irowsetnotifycp-fire-onrowchange.md)|Notifies the consumer of a change affecting the rows.|  
|[Fire\_OnRowsetChange](../../data/oledb/irowsetnotifycp-fire-onrowsetchange.md)|Notifies the consumer of a change affecting the entire rowset.|  
  
## 설명  
 `IRowsetNotifyCP`는 연결 지점 **IID\_IRowsetNotify**의 수신자에게 행 집합의 내용에 발생한 변경 내용을 알리기 위한 브로드캐스트 기능을 구현합니다.  
  
 Note that you must also implement and register `IRowsetNotify` on the consumer \(also known as the "sink"\) using [IRowsetNotifyImpl](../../data/oledb/irowsetnotifyimpl-class.md) so that the consumer can handle notifications.  See [Receiving Notifications](../../data/oledb/receiving-notifications.md) about implementing the connection point interface on the consumer.  
  
 For detailed information on implementing notifications, see "Supporting Notifications" in [Creating an Updatable Provider](../../data/oledb/creating-an-updatable-provider.md).  
  
## 요구 사항  
 **Header:** atldb.h  
  
## 참고 항목  
 [OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)   
 [Notifications \(COM\)](http://msdn.microsoft.com/library/windows/desktop/ms678433)   
 [Overview of Notifications \(OLE DB\)](https://msdn.microsoft.com/en-us/library/ms725406.aspx)   
 [BEGIN\_CONNECTION\_POINT\_MAP](../Topic/BEGIN_CONNECTION_POINT_MAP.md)   
 [END\_CONNECTION\_POINT\_MAP](../Topic/END_CONNECTION_POINT_MAP.md)   
 [CONNECTION\_POINT\_ENTRY](../Topic/CONNECTION_POINT_ENTRY.md)   
 [업데이트 가능 공급자 만들기](../../data/oledb/creating-an-updatable-provider.md)