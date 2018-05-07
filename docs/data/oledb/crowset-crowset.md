---
title: 'Crowset:: Crowset | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CRowset<TAccessor>::CRowset
- CRowset.CRowset
- ATL::CRowset::CRowset
- ATL::CRowset<TAccessor>::CRowset
- ATL.CRowset.CRowset
- CRowset
- CRowset<TAccessor>.CRowset
- CRowset::CRowset
- ATL.CRowset<TAccessor>.CRowset
dev_langs:
- C++
helpviewer_keywords:
- CRowset class, constructor
ms.assetid: 1c6f72e2-f4f4-48dc-957e-038ae8914ba7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: c1ac78caaf82dc42a5e4d4afdab7e03bad53c5f0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="crowsetcrowset"></a>CRowset::CRowset
새 `CRowset` (선택 사항)에 연결 하 고 개체는 [IRowset](https://msdn.microsoft.com/en-us/library/ms720986.aspx) 인터페이스 매개 변수로 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
      CRowset();   

CRowset(IRowset* pRowset);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pRowset`  
 [in] 이 클래스와 연결된 `IRowset` 인터페이스에 대한 포인터입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [CRowset 클래스](../../data/oledb/crowset-class.md)