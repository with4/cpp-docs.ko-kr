---
title: 'Irowsetchangeimpl:: Deleterows | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.IRowsetChangeImpl.DeleteRows
- ATL::IRowsetChangeImpl::DeleteRows
- IRowsetChangeImpl.DeleteRows
- DeleteRows
- IRowsetChangeImpl::DeleteRows
dev_langs:
- C++
helpviewer_keywords:
- DeleteRows method
ms.assetid: 462ad4f1-3b2a-4134-9733-be65708aa1d9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 6b8c8f361166d90d62aeec911aa0fd1df90b68af
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="irowsetchangeimpldeleterows"></a>IRowsetChangeImpl::DeleteRows
행 집합에서 행을 삭제합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
      STDMETHOD (DeleteRows )(HCHAPTER /* hReserved */,  
   DBCOUNTITEM cRows,  
   const HROW rghRows[],  
   DBROWSTATUS rgRowStatus[]);  
```  
  
#### <a name="parameters"></a>매개 변수  
 참조 [irowsetchange:: Deleterows](https://msdn.microsoft.com/en-us/library/ms724362.aspx) 에 *OLE DB Programmer's Reference*합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldb.h  
  
## <a name="see-also"></a>참고 항목  
 [IRowsetChangeImpl 클래스](../../data/oledb/irowsetchangeimpl-class.md)