---
title: 'Crowset:: Setdata | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.CRowset<TAccessor>.SetData
- SetData
- ATL::CRowset::SetData
- CRowset<TAccessor>.SetData
- CRowset::SetData
- ATL.CRowset.SetData
- CRowset.SetData
- CRowset<TAccessor>::SetData
- ATL::CRowset<TAccessor>::SetData
dev_langs:
- C++
helpviewer_keywords:
- SetData method
ms.assetid: 68125142-8510-4132-9393-e39efd39c784
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b8885c6e64fa7e7e22f6858d916a8e1afa8738d6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="crowsetsetdata"></a>CRowset::SetData
행의 하나 이상의 열에 데이터 값을 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT SetData() const throw();   


HRESULT SetData(int nAccessor) const throw();  
```  
  
#### <a name="parameters"></a>매개 변수  
 `nAccessor`  
 [in] 데이터에 액세스 하기 위해 사용 하는 접근자 수입니다.  
  
## <a name="return-value"></a>반환 값  
 표준 `HRESULT`입니다.  
  
## <a name="remarks"></a>설명  
 에 대 한는 `SetData` 인수 없이, 모든 접근자 양식의 업데이트에 사용 됩니다. 일반적으로 호출 **SetData** 행의 열에 있는 데이터 값을 설정 하려면 다음 호출 [업데이트](../../data/oledb/crowset-update.md) 이러한 변경 내용을 전송할 수 있습니다.  
  
 이 메서드를 사용 하려면 선택적 인터페이스 `IRowsetChange`, 모든 공급자에서 지원 되지 않는 있는;의 경우이 메서드는 반환 **E_NOINTERFACE**합니다. 설정 해야 **DBPROP_IRowsetChange** 를 `VARIANT_TRUE` 호출 하기 전에 **열려** 테이블이 나 행 집합을 포함 하는 명령입니다.  
  
 하나 이상의 열에 쓸 수 없는 경우 설정 작업이 실패할 수 있습니다. 이 문제를 해결하려면 커서 맵을 수정합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [CRowset 클래스](../../data/oledb/crowset-class.md)   
 [CRowset::Update](../../data/oledb/crowset-update.md)