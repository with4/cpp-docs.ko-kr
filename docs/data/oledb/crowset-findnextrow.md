---
title: "CRowset::FindNextRow | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL.CRowset.FindNextRow"
  - "CRowset<TAccessor>.FindNextRow"
  - "ATL::CRowset::FindNextRow"
  - "CRowset::FindNextRow"
  - "CRowset<TAccessor>::FindNextRow"
  - "CRowset.FindNextRow"
  - "ATL.CRowset<TAccessor>.FindNextRow"
  - "ATL::CRowset<TAccessor>::FindNextRow"
  - "FindNextRow"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "FindNextRow 메서드"
ms.assetid: 36484df9-3625-4f15-bf69-db73a8d91c55
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CRowset::FindNextRow
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Finds the next matching row after the specified bookmark.  
  
## 구문  
  
```  
  
      HRESULT FindNextRow(   
   DBCOMPAREOP op,   
   BYTE* pData,   
   DBTYPE wType,   
   DBLENGTH nLength,   
   BYTE bPrecision,   
   BYTE bScale,   
   BOOL bSkipCurrent = TRUE,   
   CBookmarkBase* pBookmark = NULL    
) throw( );  
```  
  
#### 매개 변수  
 `op`  
 \[in\] The operation to use in comparing row values.  For values, see [IRowsetFind::FindNextRow](https://msdn.microsoft.com/en-us/library/ms723091.aspx).  
  
 `pData`  
 \[in\] A pointer to the value to be matched.  
  
 `wType`  
 \[in\] Indicates the data type of the value part of the buffer.  For information about type indicators, see [Data Types](https://msdn.microsoft.com/en-us/library/ms723969.aspx) in the *OLE DB Programmer's Reference* in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `nLength`  
 \[in\] The length, in bytes, of the consumer data structure allocated for the data value.  For details, see the description of **cbMaxLen** in [DBBINDING Structures](https://msdn.microsoft.com/en-us/library/ms716845.aspx) in the *OLE DB Programmer's Reference.*  
  
 `bPrecision`  
 \[in\] The maximum precision used when getting data.  Used only if `wType` is `DBTYPE_NUMERIC`.  For more information, see [Conversions involving DBTYPE\_NUMERIC or DBTYPE\_DECIMAL](https://msdn.microsoft.com/en-us/library/ms719714.aspx) in the *OLE DB Programmer's Reference*.  
  
 `bScale`  
 \[in\] The scale used when getting data.  Used only if `wType` is `DBTYPE_NUMERIC` or **DBTYPE\_DECIMAL**.  For more information, see [Conversions involving DBTYPE\_NUMERIC or DBTYPE\_DECIMAL](https://msdn.microsoft.com/en-us/library/ms719714.aspx) in the *OLE DB Programmer's Reference*.  
  
 *bSkipCurrent*  
 \[in\] The number of rows from the bookmark at which to start a search.  
  
 `pBookmark`  
 \[in\] The bookmark for position at which to start a search.  
  
## 반환 값  
 A standard `HRESULT`.  
  
## 설명  
 This method requires the optional interface **IRowsetFind**, which might not be supported on all providers; if this is the case, the method returns **E\_NOINTERFACE**.  You must also set **DBPROP\_IRowsetFind** to `VARIANT_TRUE` before calling **Open** on the table or command containing the rowset.  
  
 For information about using bookmarks in consumers, see [Using Bookmarks](../../data/oledb/using-bookmarks.md).  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [CRowset 클래스](../../data/oledb/crowset-class.md)   
 [DBBINDING Structures](https://msdn.microsoft.com/en-us/library/ms716845.aspx)