---
title: 'Irowsetimpl:: Restartposition | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.IRowsetImpl.RestartPosition
- IRowsetImpl::RestartPosition
- RestartPosition
- ATL::IRowsetImpl::RestartPosition
- IRowsetImpl.RestartPosition
dev_langs:
- C++
helpviewer_keywords:
- RestartPosition method
ms.assetid: 14de66ef-8d2c-4404-adb6-3f6c74ac6cf1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1c203cc19e31f22df5903f099e953fcf5663718f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="irowsetimplrestartposition"></a>IRowsetImpl::RestartPosition
다음 인출 위치를 초기 위치로; 위치 변경 즉, 행 집합을 첫 번째 경우에 해당 위치에 만들어집니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
      STDMETHOD(RestartPosition )(HCHAPTER /* hReserved */);  
```  
  
#### <a name="parameters"></a>매개 변수  
 참조 [irowset:: Restartposition](https://msdn.microsoft.com/en-us/library/ms712877.aspx) 에 *OLE DB Programmer's Reference*합니다.  
  
## <a name="remarks"></a>설명  
 행 집합 위치까지 정의 되지 않습니다. **GetNextRow** 호출 됩니다. 이동할 수 있습니다 이전 버전과 rowet에서 호출 하 여 `RestartPosition` 및 다음 인출 또는 스크롤 뒤로 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldb.h  
  
## <a name="see-also"></a>참고 항목  
 [IRowsetImpl 클래스](../../data/oledb/irowsetimpl-class.md)