---
title: "IRowsetImpl 클래스 | Microsoft Docs"
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
  - "IRowsetImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IRowsetImpl 클래스"
ms.assetid: 6a9189af-7556-45b1-adcb-9d62bb36704c
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IRowsetImpl 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`IRowset` 인터페이스의 구현을 제공합니다.  
  
## 구문  
  
```  
template <  
   class T,   
   class RowsetInterface,  
   class RowClass = CSimpleRow,  
   class MapClass = CAtlMap <  
      RowClass::KeyType,  
      RowClass*   
   >  
>  
class ATL_NO_VTABLE IRowsetImpl : public RowsetInterface  
```  
  
#### 매개 변수  
 `T`  
 Your class, derived from `IRowsetImpl`.  
  
 `RowsetInterface`  
 A class derived from `IRowsetImpl`.  
  
 `RowClass`  
 Storage unit for the **HROW**.  
  
 `MapClass`  
 Storage unit for all row handles held by the provider.  
  
## 멤버  
  
### 메서드  
  
|||  
|-|-|  
|[AddRefRows](../../data/oledb/irowsetimpl-addrefrows.md)|기존 행 핸들에 참조 횟수를 추가합니다.|  
|[CreateRow](../../data/oledb/irowsetimpl-createrow.md)|Called by [GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md) to allocate a new **HROW**.  Not called directly by user.|  
|[GetData](../../data/oledb/irowsetimpl-getdata.md)|행 집합의 행 복사본에서 데이터를 검색합니다.|  
|[GetDBStatus](../../data/oledb/irowsetimpl-getdbstatus.md)|Returns the status for the specified field.|  
|[GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md)|이전 위치를 기억하여 행을 순서대로 페치합니다.|  
|[IRowsetImpl](../../data/oledb/irowsetimpl-class.md)|생성자입니다.  Not called directly by user.|  
|[RefRows](../../data/oledb/irowsetimpl-refrows.md)|Called by [AddRefRows](../../data/oledb/irowsetimpl-addrefrows.md) and [ReleaseRows](../../data/oledb/irowsetimpl-releaserows.md).  Not called directly by user.|  
|[ReleaseRows](../../data/oledb/irowsetimpl-releaserows.md)|행을 해제합니다.|  
|[RestartPosition](../../data/oledb/irowsetimpl-restartposition.md)|Repositions the next fetch position to its initial position; that is, its position when the rowset was first created.|  
|[SetDBStatus](../../data/oledb/irowsetimpl-setdbstatus.md)|Sets the status flags for the specified field.|  
  
### 데이터 멤버  
  
|||  
|-|-|  
|[m\_bCanFetchBack](../../data/oledb/irowsetimpl-m-bcanfetchback.md)|Indicates whether a provider supports backward fetching.|  
|[m\_bCanScrollBack](../../data/oledb/irowsetimpl-m-bcanscrollback.md)|Indicates whether a provider can have its cursor scroll backwards.|  
|[m\_bReset](../../data/oledb/irowsetimpl-m-breset.md)|Indicates whether a provider has reset its cursor position.  This has special meaning when scrolling backwards or fetching backwards in [GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md).|  
|[m\_iRowset](../../data/oledb/irowsetimpl-m-irowset.md)|An index to the rowset, representing the cursor.|  
|[m\_rgRowHandles](../../data/oledb/irowsetimpl-m-rgrowhandles.md)|A list of row handles.|  
  
## 설명  
 [IRowset](https://msdn.microsoft.com/en-us/library/ms720986.aspx) is the base rowset interface.  
  
## 요구 사항  
 **Header:** atldb.h  
  
## 참고 항목  
 [OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)