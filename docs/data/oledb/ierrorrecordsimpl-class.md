---
title: "IErrorRecordsImpl 클래스 | Microsoft Docs"
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
  - "ATL::IErrorRecordsImpl"
  - "ATL.IErrorRecordsImpl"
  - "IErrorRecordsImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IErrorRecordsImpl 클래스"
ms.assetid: dea8e938-c5d8-45ab-86de-eb8fbf534ffb
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IErrorRecordsImpl 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implements the OLE DB [IErrorRecords](https://msdn.microsoft.com/en-us/library/ms718112.aspx) interface, adding records to and retrieving records from a data member \([m\_rgErrors](../../data/oledb/ierrorrecordsimpl-m-rgerrors.md)\) of type **CAtlArray\<**`RecordClass`**\>**.  
  
## 구문  
  
```  
template <  
   class T,   
   class RecordClass = ATLERRORINFO  
>  
class IErrorRecordsImpl : public IErrorRecords  
```  
  
#### 매개 변수  
 `T`  
 A class derived from `IErrorRecordsImpl`.  
  
 `RecordClass`  
 A class that represents an OLE DB error object.  
  
## 멤버  
  
### 메서드  
  
|||  
|-|-|  
|[GetErrorDescriptionString](../../data/oledb/ierrorrecordsimpl-geterrordescriptionstring.md)|Gets the error description string from an error record.|  
|[GetErrorGUID](../../data/oledb/ierrorrecordsimpl-geterrorguid.md)|Gets the error GUID from an error record.|  
|[GetErrorHelpContext](../../data/oledb/ierrorrecordsimpl-geterrorhelpcontext.md)|Gets the help context ID from an error record.|  
|[GetErrorHelpFile](../../data/oledb/ierrorrecordsimpl-geterrorhelpfile.md)|Gets the full pathname of the help file from an error record.|  
|[GetErrorSource](../../data/oledb/ierrorrecordsimpl-geterrorsource.md)|Gets the error source code from an error record.|  
  
### Interface Methods  
  
|||  
|-|-|  
|[AddErrorRecord](../../data/oledb/ierrorrecordsimpl-adderrorrecord.md)|Adds a record to the OLE DB error object.|  
|[GetBasicErrorInfo](../../data/oledb/cdberrorinfo-getbasicerrorinfo.md)|Returns basic information about the error, such as the return code and provider\-specific error number.|  
|[GetCustomErrorObject](../../data/oledb/cdberrorinfo-getcustomerrorobject.md)|Returns a pointer to an interface on a custom error object.|  
|[GetErrorInfo](../../data/oledb/cdberrorinfo-geterrorinfo.md)|Returns an [IErrorInfo](https://msdn.microsoft.com/en-us/library/ms718112.aspx) interface pointer on the specified record.|  
|[GetErrorParameters](../../data/oledb/cdberrorinfo-geterrorparameters.md)|Returns the error parameters.|  
|[GetRecordCount](../Topic/CDaoRecordset::GetRecordCount.md)|Returns the number of records in the OLE DB record object.|  
  
### 데이터 멤버  
  
|||  
|-|-|  
|[m\_rgErrors](../../data/oledb/ierrorrecordsimpl-m-rgerrors.md)|An array of error records.|  
  
## 요구 사항  
 **Header:** atldb.h  
  
## 참고 항목  
 [OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)