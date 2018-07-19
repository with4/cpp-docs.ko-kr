---
title: 'Irowsetupdateimpl:: Undo | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.IRowsetUpdateImpl.Undo
- ATL::IRowsetUpdateImpl::Undo
- IRowsetUpdateImpl::Undo
- IRowsetUpdateImpl.Undo
dev_langs:
- C++
helpviewer_keywords:
- Undo method
ms.assetid: f3dc7764-050c-4322-9b2f-9ca772a0fb88
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: d98465d396084c157c40bdca41c3daac46bc4ad7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33104463"
---
# <a name="irowsetupdateimplundo"></a>IRowsetUpdateImpl::Undo
마지막 페치 또는 업데이트 이후 행에 변경 내용을 실행 취소합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
      STDMETHOD (Undo )(HCHAPTER /* hReserved */,  
   DBCOUNTITEM cRows,  
   const HROW rghRows[ ],  
   DBCOUNTITEM* pcRowsUndone,  
   HROW** prgRowsUndone,  
   DBROWSTATUS** prgRowStatus);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `hReserved`  
 [in] 에 해당 하는 `hChapter` 매개 변수에서 [IRowsetUpdate::Undo](https://msdn.microsoft.com/en-us/library/ms719655.aspx)합니다.  
  
 *pcRowsUndone*  
 [out] 에 해당 하는 `pcRows` 매개 변수에서 [IRowsetUpdate::Undo](https://msdn.microsoft.com/en-us/library/ms719655.aspx)합니다.  
  
 *prgRowsUndone*  
 [in] 에 해당 하는 *prgRows* 매개 변수에서 [IRowsetUpdate::Undo](https://msdn.microsoft.com/en-us/library/ms719655.aspx)합니다.  
  
 다른 매개 변수를 참조 하십시오. [IRowsetUpdate::Undo](https://msdn.microsoft.com/en-us/library/ms719655.aspx) 에 *OLE DB Programmer's Reference*합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldb.h  
  
## <a name="see-also"></a>참고 항목  
 [IRowsetUpdateImpl 클래스](../../data/oledb/irowsetupdateimpl-class.md)