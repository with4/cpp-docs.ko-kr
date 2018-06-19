---
title: 'Irowsetlocateimpl:: Getrowsat | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- GetRowsAt
- IRowsetLocateImpl.GetRowsAt
- ATL::IRowsetLocateImpl::GetRowsAt
- IRowsetLocateImpl::GetRowsAt
- ATL.IRowsetLocateImpl.GetRowsAt
dev_langs:
- C++
helpviewer_keywords:
- GetRowsAt method
ms.assetid: 6aeb09dc-3aa8-4729-97a8-144dd27063f7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e94d14e276f5ff7a24c5064fe482def49fd61335
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33105259"
---
# <a name="irowsetlocateimplgetrowsat"></a>IRowsetLocateImpl::GetRowsAt
책갈피에서의 오프셋으로 지정 된 행부터 시작 하는 행을 인출 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
      STDMETHOD (GetRowsAt )(HWATCHREGION /* hReserved1 */,  
   HCHAPTER hReserved2,  
   DBBKMARK cbBookmark,  
   const BYTE* pBookmark,  
   DBROWOFFSET lRowsOffset,  
   DBROWCOUNT cRows,  
   DBCOUNTITEM* pcRowsObtained,  
   HROW** prghRows);  
```  
  
#### <a name="parameters"></a>매개 변수  
 참조 [irowsetlocate:: Getrowsat](https://msdn.microsoft.com/en-us/library/ms723031.aspx) 에 *OLE DB Programmer's Reference*합니다.  
  
## <a name="remarks"></a>설명  
 대신 인출할 커서 위치에서 사용 하 여 [IRowset::GetRowsAt](https://msdn.microsoft.com/en-us/library/ms723031.aspx)합니다.  
  
 `IRowsetLocateImpl::GetRowsAt` 커서 위치를 변경 하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldb.h  
  
## <a name="see-also"></a>참고 항목  
 [IRowsetLocateImpl 클래스](../../data/oledb/irowsetlocateimpl-class.md)   
 [IRowsetLocateImpl::GetRowsByBookmark](../../data/oledb/irowsetlocateimpl-getrowsbybookmark.md)