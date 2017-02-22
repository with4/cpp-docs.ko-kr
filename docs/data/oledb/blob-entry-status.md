---
title: "BLOB_ENTRY_STATUS | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "BLOB_ENTRY_STATUS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BLOB_ENTRY_STATUS 매크로"
ms.assetid: 191007f4-dfcc-4ae2-a7fc-6f7899accc9f
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# BLOB_ENTRY_STATUS
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

2진 대형개체\([BLOB](https://msdn.microsoft.com/en-us/library/ms711511.aspx)\)를 바인딩하기위해 `BEGIN_COLUMN_MAP` 또는 `BEGIN_ACCESSOR_MAP`를 사용합니다.  [BLOB\_ENTRY](../../data/oledb/blob-entry.md)와 유사하지만 이 매크로는 또한 BLOB 열의 상태를 갖는다는 것은 다릅니다.  
  
## 구문  
  
```  
  
BLOB_ENTRY_STATUS(  
nOrdinal  
,   
IID  
,   
flags  
,   
data  
,   
status  
 )  
  
```  
  
#### 매개 변수  
 `nOrdinal`  
 \[in\] 열 번호입니다.  
  
 *IID*  
 \[in\] **IDD\_ISequentialStream** 와 같은 GUID 인터페이스는 BLOB을 검색할 때 사용됩니다.  
  
 `flags`  
 \[in\] OLE 구조적 저장소 모델이 지정하는 저장소 모드 플래그입니다.\(예를 들어, **STGM\_READ**\).  
  
 `data`  
 \[in\] 사용자 레코드에서 해당 데이터 멤버입니다.  
  
 *status*  
 \[out\] BLOB필드의 범위입니다.  
  
## 예제  
 [How Can I Retrieve a BLOB?](../../data/oledb/retrieving-a-blob.md) 를 참조하십시오.  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [OLE DB 소비자 템플릿에 대한 매크로 및 전역 함수](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN\_COLUMN\_MAP](../../data/oledb/begin-column-map.md)   
 [END\_COLUMN\_MAP](../../data/oledb/end-column-map.md)   
 [COLUMN\_ENTRY](../../data/oledb/column-entry.md)   
 [BLOB\_ENTRY](../../data/oledb/blob-entry.md)   
 [BLOB\_ENTRY\_LENGTH](../../data/oledb/blob-entry-length.md)   
 [BLOB\_ENTRY\_LENGTH\_STATUS](../../data/oledb/blob-entry-length-status.md)