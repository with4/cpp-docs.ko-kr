---
title: "ICommandPropertiesImpl::SetProperties | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ICommandPropertiesImpl.SetProperties"
  - "ICommandPropertiesImpl::SetProperties"
  - "SetProperties"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetProperties 메서드"
ms.assetid: c42132bb-16a9-4e00-aba6-dee785a98488
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# ICommandPropertiesImpl::SetProperties
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Sets properties for the command object.  
  
## 구문  
  
```  
  
      STDMETHOD(SetProperties)(   
   ULONG cPropertySets,   
   DBPROPSET rgPropertySets[]    
);  
```  
  
#### 매개 변수  
 See [ICommandProperties::SetProperties](https://msdn.microsoft.com/en-us/library/ms711497.aspx) in the *OLE DB Programmer's Reference*.  
  
## 요구 사항  
 **Header:** atldb.h  
  
## 참고 항목  
 [ICommandPropertiesImpl 클래스](../../data/oledb/icommandpropertiesimpl-class.md)   
 [ICommandPropertiesImpl::GetProperties](../../data/oledb/icommandpropertiesimpl-getproperties.md)