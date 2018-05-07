---
title: 'Cbulkrowset:: Setrows | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.CBulkRowset.SetRows
- CBulkRowset::SetRows
- CBulkRowset<TAccessor>.SetRows
- ATL.CBulkRowset<TAccessor>.SetRows
- CBulkRowset<TAccessor>::SetRows
- ATL::CBulkRowset<TAccessor>::SetRows
- ATL::CBulkRowset::SetRows
- CBulkRowset.SetRows
- SetRows
dev_langs:
- C++
helpviewer_keywords:
- SetRows method
ms.assetid: 7e92312a-bfd0-4c24-a799-62bef663f28e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1519c0113744bb3c1e03bec52d5504ce504ee719
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="cbulkrowsetsetrows"></a>CBulkRowset::SetRows
각 호출에 의해 검색 되는 행 핸들의 수를 설정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
      void SetRows(DBROWCOUNT nRows) throw();  
```  
  
#### <a name="parameters"></a>매개 변수  
 `nRows`  
 [in] 행 집합 (행 수)의 새 크기입니다.  
  
## <a name="remarks"></a>설명  
 이 함수를 호출 하면 행 집합을 열기 전에 이어야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [CBulkRowset 클래스](../../data/oledb/cbulkrowset-class.md)