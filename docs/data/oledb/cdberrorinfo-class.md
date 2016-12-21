---
title: "CDBErrorInfo 클래스 | Microsoft Docs"
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
  - "CDBErrorInfo"
  - "ATL::CDBErrorInfo"
  - "ATL.CDBErrorInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDBErrorInfo 클래스"
ms.assetid: 9a5c18a2-ee3e-40f5-ab4c-581288d7f737
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDBErrorInfo 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Provides support for OLE DB error processing using the OLE DB [IErrorRecords](https://msdn.microsoft.com/en-us/library/ms718112.aspx) interface.  
  
## 구문  
  
```  
class CDBErrorInfo  
```  
  
## 멤버  
  
### 메서드  
  
|||  
|-|-|  
|[GetAllErrorInfo](../../data/oledb/cdberrorinfo-getallerrorinfo.md)|Returns all error information contained in an error record.|  
|[GetBasicErrorInfo](../../data/oledb/cdberrorinfo-getbasicerrorinfo.md)|Calls [IErrorRecords::GetBasicErrorInfo](https://msdn.microsoft.com/en-us/library/ms723907.aspx) to return basic information about the specified error.|  
|[GetCustomErrorObject](../../data/oledb/cdberrorinfo-getcustomerrorobject.md)|Calls [IErrorRecords::GetCustomErrorObject](https://msdn.microsoft.com/en-us/library/ms725417.aspx) to return a pointer to an interface on a custom error object.|  
|[GetErrorInfo](../../data/oledb/cdberrorinfo-geterrorinfo.md)|Calls [IErrorRecords::GetErrorInfo](https://msdn.microsoft.com/en-us/library/ms711230.aspx) to return an **IErrorInfo** interface pointer to the specified record.|  
|[GetErrorParameters](../../data/oledb/cdberrorinfo-geterrorparameters.md)|Calls [IErrorRecords::GetErrorParameters](https://msdn.microsoft.com/en-us/library/ms715793.aspx) to return the error parameters.|  
|[GetErrorRecords](../../data/oledb/cdberrorinfo-geterrorrecords.md)|Gets error records for the specified object.|  
  
## 설명  
 This interface returns one or more error records to the user.  Call [CDBErrorInfo::GetErrorRecords](../../data/oledb/cdberrorinfo-geterrorrecords.md) first, to get a count of error records.  Then call one of the access functions, such as [CDBErrorInfo::GetAllErrorInfo](../../data/oledb/cdberrorinfo-getallerrorinfo.md), to retrieve error information for each record.  
  
## 요구 사항  
 **Header:** atldbcli.h  
  
## 참고 항목  
 [DBViewer](../../top/visual-cpp-samples.md)   
 [OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB 소비자 템플릿 참조](../../data/oledb/ole-db-consumer-templates-reference.md)