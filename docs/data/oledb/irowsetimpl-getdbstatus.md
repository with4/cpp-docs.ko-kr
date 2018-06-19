---
title: 'Irowsetimpl:: Getdbstatus | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- GetDBStatus
- IRowsetImpl.GetDBStatus
- IRowsetImpl::GetDBStatus
dev_langs:
- C++
helpviewer_keywords:
- GetDBStatus method
ms.assetid: e51d8ee2-fc0c-4909-861c-026c94fb0dfc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ebebbc2d1392e4f3c863ce366e8d19cfad3b7162
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33106533"
---
# <a name="irowsetimplgetdbstatus"></a>IRowsetImpl::GetDBStatus
반환 된 `DBSTATUS` 지정된 된 필드에 대 한 상태 플래그입니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
      virtual DBSTATUS GetDBStatus(RowClass* currentRow,  
   ATLCOLUMNINFO* columnNames);  
```  
  
#### <a name="parameters"></a>매개 변수  
 [in] `currentRow`  
 현재 행입니다.  
  
 [in] `columnNames`  
 상태가 요청 되는 열입니다.  
  
## <a name="return-value"></a>반환 값  
 [DBSTATUS](https://msdn.microsoft.com/en-us/library/ms722617.aspx) 열에 대 한 플래그입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldb.h  
  
## <a name="see-also"></a>참고 항목  
 [IRowsetImpl 클래스](../../data/oledb/irowsetimpl-class.md)