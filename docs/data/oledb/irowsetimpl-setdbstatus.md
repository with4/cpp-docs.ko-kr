---
title: 'Irowsetimpl:: Setdbstatus | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IRowsetImpl.SetDBStatus
- IRowsetImpl::SetDBStatus
- SetDBStatus
dev_langs:
- C++
helpviewer_keywords:
- SetDBStatus method
ms.assetid: b73f526a-4fc6-4adb-9611-c3cca2cddb23
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7e6e07b6fe1a45a779c5ffe1e1afffaabdcb6d34
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="irowsetimplsetdbstatus"></a>IRowsetImpl::SetDBStatus
설정 된 `DBSTATUS` 지정된 된 필드에 대 한 상태 플래그입니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
      virtual HRESULT SetDBStatus(DBSTATUS* statusFlags,  
   RowClass* currentRow,  
   ATLCOLUMNINFO* columnInfo);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `statusFlags`  
 [DBSTATUS](https://msdn.microsoft.com/en-us/library/ms722617.aspx) 열에 대해 설정할 플래그입니다.  
  
 `currentRow`  
 현재 행입니다.  
  
 *columnInfo*  
 상태가 설정 되는 열입니다.  
  
## <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
## <a name="remarks"></a>설명  
 공급자에 대 한 특수 한 처리를 제공 하려면이 함수를 재정의 **DBSTATUS_S_ISNULL** 및 **DBSTATUS_S_DEFAULT**합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldb.h  
  
## <a name="see-also"></a>참고 항목  
 [IRowsetImpl 클래스](../../data/oledb/irowsetimpl-class.md)