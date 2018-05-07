---
title: 'Crowset:: Updateall | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CRowset::UpdateAll
- ATL.CRowset.UpdateAll
- CRowset<TAccessor>.UpdateAll
- ATL.CRowset<TAccessor>.UpdateAll
- UpdateAll
- CRowset.UpdateAll
- ATL::CRowset<TAccessor>::UpdateAll
- CRowset<TAccessor>::UpdateAll
- ATL::CRowset::UpdateAll
dev_langs:
- C++
helpviewer_keywords:
- UpdateAll method
ms.assetid: e5b26c0a-40fc-4c91-a293-5084951788e6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: d9e21cd34a4d758becb12b529fe858e96d18f187
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="crowsetupdateall"></a>CRowset::UpdateAll
보류 중인 마지막 인출 이후 모든 행에 대해 변경 내용을 전송 또는 **업데이트** 호출 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT UpdateAll(DBCOUNTITEM* pcRows = NULL,   
   HROW** pphRow = NULL,   
   DBROWSTATUS** ppStatus = NULL) throw();  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pcRows`  
 [out] 위치에 대 한 포인터를 `UpdateAll` 필요한 경우 업데이트를 시도 하는 행 수를 반환 합니다.  
  
 `pphRow`  
 [out] 메모리에 대 한 포인터 `UpdateAll` 를 업데이트 하려고 시도 하는 행의 핸들을 반환 합니다. 핸들이 없는 경우 반환 됩니다 `pphRow` null입니다.  
  
 `ppStatus`  
 [out] 위치에 대 한 포인터를 **업데이트** 행 상태 값을 반환 합니다. 상태가 반환 됩니다 `ppStatus` null입니다.  
  
## <a name="remarks"></a>설명  
 보류 중인 변경 이후 행 인출 된 마지막 또는 사용 하 여 업데이트할 모든 행에 대해 전송 [업데이트](../../data/oledb/crowset-update.md) 또는 `UpdateAll`합니다. `UpdateAll` 수정 된, 여전히이 핸들에 대 한 모든 행을 업데이트 합니다 (참조 `pphRow`) 여부.  
  
 예를 들어, 사용 하는 경우 **삽입** 호출 하거나 할 수는 행 집합의 5 개의 행을 삽입 하려면 **업데이트** 5 번 또는 호출 `UpdateAll` 업데이트 모두에 한 번입니다.  
  
 이 메서드를 사용 하려면 선택적 인터페이스 `IRowsetUpdate`, 모든 공급자에서 지원 되지 않는 있는;의 경우이 메서드는 반환 **E_NOINTERFACE**합니다. 설정 해야 **DBPROP_IRowsetUpdate** 를 `VARIANT_TRUE` 호출 하기 전에 **열려** 테이블이 나 행 집합을 포함 하는 명령입니다.  
  
## <a name="return-value"></a>반환 값  
 표준 `HRESULT`입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [CRowset 클래스](../../data/oledb/crowset-class.md)   
 [IRowsetUpdate::Update](https://msdn.microsoft.com/en-us/library/ms719709.aspx)   
 [CRowset::SetData](../../data/oledb/crowset-setdata.md)   
 [CRowset::Update](../../data/oledb/crowset-update.md)