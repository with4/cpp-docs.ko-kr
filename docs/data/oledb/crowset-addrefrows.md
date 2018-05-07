---
title: 'Crowset:: Addrefrows | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CRowset<TAccessor>.AddRefRows
- CRowset.AddRefRows
- ATL.CRowset.AddRefRows
- AddRefRows
- CRowset::AddRefRows
- CRowset<TAccessor>::AddRefRows
- ATL::CRowset::AddRefRows
- ATL.CRowset<TAccessor>.AddRefRows
- ATL::CRowset<TAccessor>::AddRefRows
dev_langs:
- C++
helpviewer_keywords:
- AddRefRows method
ms.assetid: 590b5a24-870f-4c42-b0c8-28491f368a82
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f41a33523f30776109624982b9de1a57d4d9227b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="crowsetaddrefrows"></a>CRowset::AddRefRows
호출 [irowset:: Addrefrows](https://msdn.microsoft.com/en-us/library/ms719619.aspx) 현재 행 핸들와 관련 된 참조 횟수를 1) (씩 증가 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT AddRefRows() throw();  
  
```  
  
## <a name="return-value"></a>반환 값  
 표준 `HRESULT`입니다.  
  
## <a name="remarks"></a>설명  
 이 메서드는 현재 행 핸들에 대 한 참조 횟수를 증가 시킵니다. 호출 [ReleaseRows](../../data/oledb/crowset-releaserows.md) 여 횟수를 줄여야 합니다. Move 메서드에서 반환 된 행 하나의 참조 수 있으며  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [CRowset 클래스](../../data/oledb/crowset-class.md)   
 [CRowset::ReleaseRows](../../data/oledb/crowset-releaserows.md)