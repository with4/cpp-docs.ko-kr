---
title: "IRowsetUpdateImpl 클래스 | Microsoft Docs"
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
  - "IRowsetUpdateImpl"
  - "ATL.IRowsetUpdateImpl"
  - "ATL::IRowsetUpdateImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IRowsetUpdateImpl 클래스"
  - "공급자, 업데이트 가능"
  - "업데이트 가능 공급자, 연기된 업데이트"
ms.assetid: f85af76b-ab6f-4f8b-8f4a-337c9679d68f
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IRowsetUpdateImpl 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

The OLE DB Templates implementation of the [IRowsetUpdate](https://msdn.microsoft.com/en-us/library/ms714401.aspx) interface.  
  
## 구문  
  
```  
template <  
   class T,   
   class Storage,   
   class UpdateArray = CAtlArray<Storage>,   
   class RowClass = CSimpleRow,   
   class MapClass = CAtlMap <RowClass::KeyType, RowClass*>   
>  
class IRowsetUpdateImpl : public IRowsetChangeImpl<  
   T,   
   Storage,   
   IRowsetUpdate,   
   RowClass,   
   MapClass  
>  
```  
  
#### 매개 변수  
 `T`  
 A class derived from `IRowsetUpdateImpl`.  
  
 `Storage`  
 The user record.  
  
 `UpdateArray`  
 An array containing cached data for updating the rowset.  
  
 `RowClass`  
 The storage unit for the **HROW**.  
  
 `MapClass`  
 The storage unit for all row handles held by the provider.  
  
## 멤버  
  
### Interface Methods \(Used with IRowsetChange\)  
  
|||  
|-|-|  
|[SetData](../../data/oledb/irowsetupdateimpl-setdata.md)|Sets data values in one or more columns.|  
  
### Interface Methods \(Used with IRowsetUpdate\)  
  
|||  
|-|-|  
|[GetOriginalData](../../data/oledb/irowsetupdateimpl-getoriginaldata.md)|Gets the data most recently transmitted to or obtained from the data source, ignoring pending changes.|  
|[GetPendingRows](../../data/oledb/irowsetupdateimpl-getpendingrows.md)|Returns a list of rows with pending changes.|  
|[GetRowStatus](../../data/oledb/irowsetupdateimpl-getrowstatus.md)|Returns the status of specified rows.|  
|[실행 취소](../../data/oledb/irowsetupdateimpl-undo.md)|Undoes any changes to the row since the last fetch or update.|  
|[Update](../../data/oledb/irowsetupdateimpl-update.md)|Transmits any changes made to the row since the last fetch or update.|  
  
### Implementation Methods \(Callback\)  
  
|||  
|-|-|  
|[IsUpdateAllowed](../../data/oledb/irowsetupdateimpl-isupdateallowed.md)|Used to check for security, integrity, and so on before allowing updates.|  
  
### 데이터 멤버  
  
|||  
|-|-|  
|[m\_mapCachedData](../../data/oledb/irowsetupdateimpl-m-mapcacheddata.md)|Contains the original data for the deferred operation.|  
  
## 설명  
 You should first read and understand the documentation for [IRowsetChange](https://msdn.microsoft.com/en-us/library/ms715790.aspx), because everything described there also applies here.  You should also read chapter 6 of the `OLE``DB``Programmer's``Reference` on setting data.  
  
 `IRowsetUpdateImpl` implements the OLE DB `IRowsetUpdate` interface, which enables consumers to delay the transmission of changes made with `IRowsetChange` to the data source and undo changes before transmission.  
  
> [!IMPORTANT]
>  It is strongly recommended that you read the following documentation BEFORE attempting to implement your provider:  
  
-   [Creating an Updatable Provider](../../data/oledb/creating-an-updatable-provider.md)  
  
-   Chapter 6 of the `OLE``DB``Programmer's``Reference`  
  
-   Also see how the `RUpdateRowset` class is used in the UpdatePV sample  
  
## 요구 사항  
 **Header:** atldb.h  
  
## 참고 항목  
 [OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)   
 [업데이트 가능 공급자 만들기](../../data/oledb/creating-an-updatable-provider.md)