---
title: "COLUMN_ENTRY_LENGTH | Microsoft Docs"
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
  - "COLUMN_ENTRY_LENGTH"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COLUMN_ENTRY_LENGTH 매크로"
ms.assetid: 1758babf-204c-4d1d-b82a-f9a607072e9a
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COLUMN_ENTRY_LENGTH
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

데이터베이스의 특정 열에는 행 집합의 바인딩을 나타냅니다.  
  
## 구문  
  
```  
  
COLUMN_ENTRY_LENGTH(  
nOrdinal  
,   
data  
,   
length  
 )  
  
```  
  
#### 매개 변수  
 *OLE DB Programmer's Reference* 의 [DBBINDING](https://msdn.microsoft.com/en-us/library/ms716845.aspx) 를 참조하십시오.  
  
 `nOrdinal`  
 \[in\] 열 번호, 1부터 시작합니다.  Bookmark는 0 번 열에 해당합니다.  
  
 `data`  
 \[in\] 사용자 레코드에서 해당 데이터 멤버입니다.  
  
 *length*  
 \[in\] 열 길이에 바인딩되는 변수입니다.  
  
## 설명  
 이 매크로는 *길이* 변수를 지원합니다.  구체적으로는 다음과 같이 사용되고 있습니다.  
  
-   [BEGIN\_COLUMN\_MAP](../../data/oledb/begin-column-map.md) 및 [END\_COLUMN\_MAP](../../data/oledb/end-column-map.md) 매크로 사이입니다.  
  
-   [BEGIN\_ACCESSOR](../../data/oledb/begin-accessor.md) 및 [END\_ACCESSOR](../../data/oledb/end-accessor.md) 매크로 사이입니다.  
  
-   [BEGIN\_PARAM\_MAP](../../data/oledb/begin-param-map.md) 및 [END\_PARAM\_MAP](../../data/oledb/end-param-map.md) 매크로 사이입니다.  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [OLE DB 소비자 템플릿에 대한 매크로 및 전역 함수](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN\_ACCESSOR](../../data/oledb/begin-accessor.md)   
 [BEGIN\_ACCESSOR\_MAP](../../data/oledb/begin-accessor-map.md)   
 [BEGIN\_COLUMN\_MAP](../../data/oledb/begin-column-map.md)   
 [COLUMN\_ENTRY](../../data/oledb/column-entry.md)   
 [COLUMN\_ENTRY\_EX](../../data/oledb/column-entry-ex.md)   
 [COLUMN\_ENTRY\_PS](../../data/oledb/column-entry-ps.md)   
 [COLUMN\_ENTRY\_PS\_LENGTH](../../data/oledb/column-entry-ps-length.md)   
 [COLUMN\_ENTRY\_LENGTH\_STATUS](../../data/oledb/column-entry-length-status.md)   
 [COLUMN\_ENTRY\_PS\_LENGTH\_STATUS](../../data/oledb/column-entry-ps-length-status.md)   
 [COLUMN\_ENTRY\_STATUS](../../data/oledb/column-entry-status.md)   
 [COLUMN\_ENTRY\_PS\_STATUS](../../data/oledb/column-entry-ps-status.md)   
 [END\_ACCESSOR](../../data/oledb/end-accessor.md)   
 [END\_ACCESSOR\_MAP](../../data/oledb/end-accessor-map.md)   
 [END\_COLUMN\_MAP](../../data/oledb/end-column-map.md)