---
title: 'Cbulkrowset:: Releaserows | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ReleaseRows
- ATL.CBulkRowset<TAccessor>.ReleaseRows
- ATL::CBulkRowset<TAccessor>::ReleaseRows
- ATL.CBulkRowset.ReleaseRows
- CBulkRowset<TAccessor>::ReleaseRows
- ATL::CBulkRowset::ReleaseRows
- CBulkRowset::ReleaseRows
- CBulkRowset.ReleaseRows
dev_langs:
- C++
helpviewer_keywords:
- ReleaseRows method
ms.assetid: ba48aff3-0887-47ba-aed7-7ff28fa1c4a8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a00de4950445a0d16c43d46a486390c152029de6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33094929"
---
# <a name="cbulkrowsetreleaserows"></a>CBulkRowset::ReleaseRows
호출 [irowset:: Releaserows](https://msdn.microsoft.com/en-us/library/ms719771.aspx) bulk 행 집합에서 현재 검색 된 모든 행에 대 한 참조 횟수를 줄여야 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT ReleaseRows() throw();  
  
```  
  
## <a name="return-value"></a>반환 값  
 표준 `HRESULT`입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [CBulkRowset 클래스](../../data/oledb/cbulkrowset-class.md)   
 [CBulkRowset::AddRefRows](../../data/oledb/cbulkrowset-addrefrows.md)