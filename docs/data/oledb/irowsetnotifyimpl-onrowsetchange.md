---
title: "IRowsetNotifyImpl::OnRowsetChange | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "OnRowsetChange"
  - "IRowsetNotifyImpl::OnRowsetChange"
  - "IRowsetNotifyImpl.OnRowsetChange"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OnRowsetChange 메서드"
ms.assetid: 5125b0c8-f175-4ee6-befa-8df2c904d5e0
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# IRowsetNotifyImpl::OnRowsetChange
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

전체 행 집합에 영향을 주는 모든 변경 사항을 소비자에게 알립니다.  
  
## 구문  
  
```  
  
   STDMETHOD(OnRowsetChange)(   
/* [in] */ IRowset* /* pRowset */,  
/* [in] */ DBREASON /* eReason */,  
/* [in] */ DBEVENTPHASE /* ePhase */,  
/* [in] */ BOOL /* fCantDeny */)  
```  
  
#### 매개 변수  
 See [IRowsetNotify::OnRowsetChange](https://msdn.microsoft.com/en-us/library/ms722669.aspx) for parameter descriptions.  
  
## 반환 값  
 See [IRowsetNotify::OnRowsetChange](https://msdn.microsoft.com/en-us/library/ms722669.aspx) for return value descriptions.  
  
## 설명  
 This method wraps the [IRowsetNotify::OnRowsetChange](https://msdn.microsoft.com/en-us/library/ms722669.aspx) method.  See that method's description in the OLE DB Programmer's Reference for details.  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [IRowsetNotifyImpl 클래스](../../data/oledb/irowsetnotifyimpl-class.md)   
 [IRowsetNotify::OnRowsetChange](https://msdn.microsoft.com/en-us/library/ms722669.aspx)