---
title: "IRowsetNotifyImpl 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL.IRowsetNotifyImpl"
  - "ATL::IRowsetNotifyImpl"
  - "IRowsetNotifyImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IRowsetNotifyImpl 클래스"
ms.assetid: fbfd0cb2-38ff-4b42-899a-8de902f834b8
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# IRowsetNotifyImpl 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implements and registers [IRowsetNotify](https://msdn.microsoft.com/en-us/library/ms712959.aspx) on the consumer \(also known as the "sink"\) so that it can handle notifications.  
  
## 구문  
  
```  
class ATL_NO_VTABLE IRowsetNotifyImpl : public IRowsetNotify  
```  
  
## 멤버  
  
### 메서드  
  
|||  
|-|-|  
|[OnFieldChange](../../data/oledb/irowsetnotifyimpl-onfieldchange.md)|열 값에 대한 모든 변경 사항을 소비자에게 알립니다.|  
|[OnRowChange](../../data/oledb/irowsetnotifyimpl-onrowchange.md)|행의 첫 번째 변경 사항이나 전체 행에 영향을 주는 모든 변경 사항을 소비자에게 알립니다.|  
|[OnRowsetChange](../../data/oledb/irowsetnotifyimpl-onrowsetchange.md)|전체 행 집합에 영향을 주는 모든 변경 사항을 소비자에게 알립니다.|  
  
## 설명  
 See [Receiving Notifications](../../data/oledb/receiving-notifications.md) about implementing the connection point interface on the consumer.  
  
 `IRowsetNotifyImpl` provides a dummy implementation for `IRowsetNotify`, with empty functions for the `IRowsetNotify` methods [OnFieldChange](https://msdn.microsoft.com/en-us/library/ms715961.aspx), [OnRowChange](https://msdn.microsoft.com/en-us/library/ms722694.aspx), and [OnRowsetChange](https://msdn.microsoft.com/en-us/library/ms722669.aspx).  If you inherit from this class when you implement an `IRowsetNotify` interface, you can implement only the methods you need.  You also need to provide empty implementations for the other methods yourself.  
  
## 요구 사항  
 **Header:** atldbcli.h  
  
## 참고 항목  
 [OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [IRowsetNotify](https://msdn.microsoft.com/en-us/library/ms712959.aspx)   
 [IRowsetNotifyCP 클래스](../../data/oledb/irowsetnotifycp-class.md)