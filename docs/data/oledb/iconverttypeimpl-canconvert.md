---
title: "IConvertTypeImpl::CanConvert | Microsoft Docs"
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
  - "IConvertTypeImpl.CanConvert"
  - "CanConvert"
  - "IConvertTypeImpl::CanConvert"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CanConvert 메서드"
ms.assetid: bdad6e95-bc0b-4427-9b5e-eea51f09f392
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IConvertTypeImpl::CanConvert
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gives information on the availability of type conversions on a command or on a rowset.  
  
## 구문  
  
```  
  
      STDMETHOD(CanConvert)(   
   DBTYPE wFromType,   
   DBTYPE wToType,   
   DBCONVERTFLAGS dwConvertFlags    
);  
```  
  
#### 매개 변수  
 See [IConvertType::CanConvert](https://msdn.microsoft.com/en-us/library/ms711224.aspx) in the *OLE DB Programmer's Reference*.  
  
## 설명  
 Uses OLE DB data conversion in `MSADC.DLL`.  
  
## 요구 사항  
 **Header:** atldb.h  
  
## 참고 항목  
 [IConvertTypeImpl 클래스](../../data/oledb/iconverttypeimpl-class.md)