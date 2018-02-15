---
title: IRowsetLocateImpl::GetRowsByBookmark | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IRowsetLocateImpl::GetRowsByBookmark
- IRowsetLocateImpl.GetRowsByBookmark
- GetRowsByBookmark
dev_langs:
- C++
helpviewer_keywords:
- GetRowsByBookmark method
ms.assetid: 07906e42-3582-427e-812a-aa19791e3c56
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f76bbcbe13ccbdcb19a1ba8452804810066c9f5b
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="irowsetlocateimplgetrowsbybookmark"></a>IRowsetLocateImpl::GetRowsByBookmark
지정 된 책갈피를 일치 하는 하나 이상의 행을 인출 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
      STDMETHOD (GetRowsByBookmark )(HCHAPTER /* hReserved */,  
   DBCOUNTITEM cRows,  
   const DBBKMARK rgcbBookmarks[],  
   const BYTE* rgpBookmarks,  
   HROW rghRows[],  
   DBROWSTATUS* rgRowStatus[]);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `hReserved`  
 [in] 에 해당 `hChapter` 매개 변수를 [irowsetlocate:: Getrowsbybookmark](https://msdn.microsoft.com/en-us/library/ms725420.aspx)합니다.  
  
 다른 매개 변수를 참조 하십시오. [irowsetlocate:: Getrowsbybookmark](https://msdn.microsoft.com/en-us/library/ms725420.aspx) 에 *OLE DB Programmer's Reference*합니다.  
  
## <a name="remarks"></a>설명  
 책갈피는 정의 하는 값 또는 OLE DB 수 [표준 책갈피](https://msdn.microsoft.com/en-us/library/ms712954.aspx) (**DBBMK_FIRST** 또는 **DBBMK_LAST**). 커서 위치를 변경 하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldb.h  
  
## <a name="see-also"></a>참고 항목  
 [IRowsetLocateImpl 클래스](../../data/oledb/irowsetlocateimpl-class.md)   
 [IRowsetLocateImpl::GetRowsAt](../../data/oledb/irowsetlocateimpl-getrowsat.md)