---
title: "CDynamicParameterAccessor::SetParamStatus | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDynamicParameterAccessor::SetParamStatus"
  - "ATL.CDynamicParameterAccessor.SetParamStatus"
  - "ATL::CDynamicParameterAccessor::SetParamStatus"
  - "CDynamicParameterAccessor.SetParamStatus"
  - "SetParamStatus"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetParamStatus 메서드"
ms.assetid: 0c2271f6-457d-46ca-88b7-4590aadb20d7
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CDynamicParameterAccessor::SetParamStatus
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

지정된 된 매개 변수는 버퍼에 저장 된 상태를 설정 합니다.  
  
## 구문  
  
```  
  
      bool SetParamStatus(  
   DBORDINAL nParam,  
   DBSTATUS status  
);  
```  
  
#### 매개 변수  
 `nParam`  
 \[in\] 매개 변수 번호 \(1에서 오프셋\)입니다.  매개 변수 0은 반환 값으로 예약 됩니다.  매개 변수 번호는 SQL 또는 저장된 프로시저 호출의 순서에 따라 매개 변수의 인덱스입니다.  예제를 보려면 [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) 를 참조하십시오.  
  
 *status*  
 \[in\] 지정된 매개 변수의 `DBSTATUS` 상태입니다.  `DBSTATUS` 값에 대한 자세한 정보는 *OLE DB Programmer's Reference* 의 [Status](https://msdn.microsoft.com/en-us/library/ms722617.aspx) 를 참조하거나 oledb.h에서 `DBSTATUS` 를 검색하십시오.  
  
## 설명  
 성공하면 **true**를 반환하고 또는 실패하면 **false**를 반환합니다.  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [CDynamicParameterAccessor 클래스](../../data/oledb/cdynamicparameteraccessor-class.md)