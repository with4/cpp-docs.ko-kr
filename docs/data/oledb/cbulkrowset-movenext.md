---
title: 'Cbulkrowset:: Movenext | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.CBulkRowset<TAccessor>.MoveNext
- ATL::CBulkRowset::MoveNext
- CBulkRowset::MoveNext
- ATL.CBulkRowset.MoveNext
- CBulkRowset.MoveNext
- ATL::CBulkRowset<TAccessor>::MoveNext
- CBulkRowset<TAccessor>.MoveNext
- CBulkRowset<TAccessor>::MoveNext
dev_langs:
- C++
helpviewer_keywords:
- MoveNext method
ms.assetid: 788f3344-cf60-4af1-8f5f-0098c8d1a3f0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 68ec7e4a583039a0087654dadde36598a3ced629
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="cbulkrowsetmovenext"></a>CBulkRowset::MoveNext
데이터의 다음 행을 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT MoveNext() throw();  
  
```  
  
## <a name="return-value"></a>반환 값  
 표준 `HRESULT`입니다. 행 집합의 끝에 도달한 경우 반환 **DB_S_ENDOFROWSET**합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [CBulkRowset 클래스](../../data/oledb/cbulkrowset-class.md)