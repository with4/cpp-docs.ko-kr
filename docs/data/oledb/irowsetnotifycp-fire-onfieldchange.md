---
title: "IRowsetNotifyCP::Fire_OnFieldChange | Microsoft Docs"
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
  - "Fire_OnFieldChange"
  - "ATL::IRowsetNotifyCP::Fire_OnFieldChange"
  - "ATL.IRowsetNotifyCP.Fire_OnFieldChange"
  - "IRowsetNotifyCP.Fire_OnFieldChange"
  - "IRowsetNotifyCP::Fire_OnFieldChange"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Fire_OnFieldChange 메서드"
ms.assetid: 03dad058-8d4f-4113-aea4-ef7764eab9ec
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IRowsetNotifyCP::Fire_OnFieldChange
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[OnFieldChange](https://msdn.microsoft.com/en-us/library/ms715961.aspx) 의 열 값 변경에 대 한 소비자를 알리는 이벤트를 브로드캐스트합니다.  
  
## 구문  
  
```  
  
      HRESULT Fire_OnFieldChange(  
   IRowset* pRowset,  
   HROW hRow,  
   DBORDINAL cColumns,  
   DBORDINAL* rgColumns,  
   DBREASON eReason,  
   DBEVENTPHASE ePhase,  
   BOOL fCantDeny   
);  
```  
  
#### 매개 변수  
 자세한 내용은 *OLE DB Programmer's Reference*에 있는 [IRowsetNotify::OnFieldChange](https://msdn.microsoft.com/en-us/library/ms715961.aspx)를 참조하십시오.  
  
## 요구 사항  
 **Header:** atldb.h  
  
## 참고 항목  
 [IRowsetNotifyCP 클래스](../../data/oledb/irowsetnotifycp-class.md)