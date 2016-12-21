---
title: "CDBErrorInfo::GetAllErrorInfo | Microsoft Docs"
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
  - "ATL.CDBErrorInfo.GetAllErrorInfo"
  - "CDBErrorInfo::GetAllErrorInfo"
  - "ATL::CDBErrorInfo::GetAllErrorInfo"
  - "GetAllErrorInfo"
  - "CDBErrorInfo.GetAllErrorInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetAllErrorInfo 메서드"
ms.assetid: 630049fa-d296-497a-bbf6-f5d3d71d271d
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDBErrorInfo::GetAllErrorInfo
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Returns all the types of error information contained in an error record.  
  
## 구문  
  
```  
  
      HRESULT GetAllErrorInfo(  
   ULONG ulRecordNum,  
   LCID lcid,  
   BSTR* pbstrDescription,  
   BSTR* pbstrSource = NULL,  
   GUID* pguid = NULL,  
   DWORD* pdwHelpContext = NULL,  
   BSTR* pbstrHelpFile = NULL  
) const throw( );  
```  
  
#### 매개 변수  
 *ulRecordNum*  
 \[in\] The zero\-based number of the record for which to return error information.  
  
 `lcid`  
 \[in\] The locale ID for the error information to be returned.  
  
 `pbstrDescription`  
 \[out\] A pointer to a text description of the error or NULL if the locale is not supported.  설명 부분을 참조하십시오.  
  
 `pbstrSource`  
 \[out\] A pointer to a string containing the name of the component that generated the error.  
  
 `pguid`  
 \[out\] A pointer to the GUID of the interface that defined the error.  
  
 *pdwHelpContext*  
 \[out\] A pointer to the help context ID for the error.  
  
 *pbstrHelpFile*  
 \[out\] A pointer to a string containing the path to the help file that describes the error.  
  
## 반환 값  
 성공하면 `S_OK`입니다.  See [IErrorRecords::GetErrorInfo](https://msdn.microsoft.com/en-us/library/ms711230.aspx) in the *OLE DB Programmer's Reference* for other return values.  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 설명  
 The output value of `pbstrDescription` is obtained internally by calling IErrorInfo::GetDescription, which sets the value to NULL if the locale is not supported, or if both of the following conditions are true:  
  
1.  the value of `lcid` is NOT U.S. English and  
  
2.  the value of `lcid` is NOT equal to the value returned by GetUserDefaultLCID.  
  
## 참고 항목  
 [CDBErrorInfo 클래스](../../data/oledb/cdberrorinfo-class.md)