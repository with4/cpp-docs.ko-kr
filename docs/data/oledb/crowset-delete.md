---
title: 'Crowset:: Delete | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::CRowset::Delete
- CRowset.Delete
- CRowset::Delete
- ATL.CRowset.Delete
- ATL::CRowset<TAccessor>::Delete
- CRowset<TAccessor>.Delete
- CRowset<TAccessor>::Delete
- ATL.CRowset<TAccessor>.Delete
dev_langs:
- C++
helpviewer_keywords:
- Delete method
ms.assetid: 4feb4f7e-139f-489a-b7d5-ea6ec0058e0f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 3554dea7c8054a7deb19e0419f9b6134d649fe7d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33098279"
---
# <a name="crowsetdelete"></a>CRowset::Delete
호출 [irowsetchange:: Deleterows](https://msdn.microsoft.com/en-us/library/ms724362.aspx) 행 집합에서 현재 행을 삭제 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT Delete() const throw();  
  
```  
  
## <a name="return-value"></a>반환 값  
 표준 `HRESULT`입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [CRowset 클래스](../../data/oledb/crowset-class.md)