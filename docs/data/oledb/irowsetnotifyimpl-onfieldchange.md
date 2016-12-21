---
title: "IRowsetNotifyImpl::OnFieldChange | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IRowsetNotifyImpl.OnFieldChange"
  - "IRowsetNotifyImpl::OnFieldChange"
  - "OnFieldChange"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OnFieldChange 메서드"
ms.assetid: f26b492c-c86e-423b-9374-175e510a2860
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IRowsetNotifyImpl::OnFieldChange
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

열 값에 대한 모든 변경 사항을 소비자에게 알립니다.  
  
## 구문  
  
```  
  
STDMETHOD(OnFieldChange)(   
/* [in] */ IRowset* /* pRowset */,  
/* [in] */ HROW /* hRow */,  
/* [in] */ DBORDINAL /* cColumns */,  
/* [size_is][in] */ DBORDINAL /* rgColumns */ [] ,  
/* [in] */ DBREASON /* eReason */,  
/* [in] */ DBEVENTPHASE /* ePhase */,  
/* [in] */ BOOL /* fCantDeny */)  
```  
  
#### 매개 변수  
 See [IRowsetNotify::OnFieldChange](https://msdn.microsoft.com/en-us/library/ms715961.aspx) for parameter descriptions.  
  
## 반환 값  
 See [IRowsetNotify::OnFieldChange](https://msdn.microsoft.com/en-us/library/ms715961.aspx) for return value descriptions.  
  
## 설명  
 This method wraps the [IRowsetNotify::OnFieldChange](https://msdn.microsoft.com/en-us/library/ms715961.aspx) method.  See that method's description in the OLE DB Programmer's Reference for details.  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [IRowsetNotifyImpl 클래스](../../data/oledb/irowsetnotifyimpl-class.md)   
 [IRowsetNotify::OnFieldChange](https://msdn.microsoft.com/en-us/library/ms715961.aspx)