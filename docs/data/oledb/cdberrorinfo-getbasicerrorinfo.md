---
title: "CDBErrorInfo::GetBasicErrorInfo | Microsoft Docs"
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
  - "CDBErrorInfo::GetBasicErrorInfo"
  - "ATL.CDBErrorInfo.GetBasicErrorInfo"
  - "CDBErrorInfo.GetBasicErrorInfo"
  - "ATL::CDBErrorInfo::GetBasicErrorInfo"
  - "GetBasicErrorInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetBasicErrorInfo 메서드"
ms.assetid: 263cec53-63f6-48fe-b46e-31d20251863e
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDBErrorInfo::GetBasicErrorInfo
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[IErrorRecords::GetBasicErrorInfo](https://msdn.microsoft.com/en-us/library/ms723907.aspx)을 호출하여  공급자별 오류 번호 반환 코드 등의 오류에 대한 기본 정보를 반환합니다.  
  
## 구문  
  
```  
  
      HRESULT GetBasicErrorInfo(   
   ULONG ulRecordNum,   
   ERRORINFO* pErrorInfo    
) const throw( );  
```  
  
#### 매개 변수  
 자세한 내용은 *OLE DB Programmer's Reference*에 있는 [IErrorRecords::GetBasicErrorInfo](https://msdn.microsoft.com/en-us/library/ms723907.aspx)를 참조하십시오.  
  
## 반환 값  
 표준 `HRESULT`입니다.  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [CDBErrorInfo 클래스](../../data/oledb/cdberrorinfo-class.md)