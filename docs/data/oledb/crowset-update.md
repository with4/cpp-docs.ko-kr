---
title: 'Crowset:: Update | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CRowset.Update
- ATL.CRowset.Update
- ATL.CRowset<TAccessor>.Update
- ATL::CRowset<TAccessor>::Update
- CRowset<TAccessor>::Update
- CRowset::Update
- CRowset<TAccessor>.Update
- ATL::CRowset::Update
dev_langs:
- C++
helpviewer_keywords:
- Update method
ms.assetid: cd5fedc8-2b85-4cb8-8c40-c79576316903
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ac465bdb5cfa228e5621a3ccf0d791f5f5271421
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="crowsetupdate"></a>CRowset::Update
보류 중인 마지막 인출 이후 현재 행에 대해 변경 내용을 전송 또는 **업데이트** 호출 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT Update(DBCOUNTITEM* pcRows = NULL,   
   HROW* phRow = NULL,   
   DBROWSTATUS* pStatus = NULL) throw();  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pcRows`  
 [out] 위치에 대 한 포인터를 **업데이트** 필요한 경우 업데이트를 시도 하는 행 수를 반환 합니다.  
  
 `phRow`  
 [out] 위치에 대 한 포인터를 **업데이트** 를 업데이트 하려고 시도 하는 행의 핸들을 반환 합니다. 핸들이 없는 경우 반환 됩니다 `phRow` null입니다.  
  
 `pStatus`  
 [out] 위치에 대 한 포인터를 **업데이트** 행 상태 값을 반환 합니다. 상태가 반환 됩니다 `pStatus` null입니다.  
  
## <a name="return-value"></a>반환 값  
 표준 `HRESULT`입니다.  
  
## <a name="remarks"></a>설명  
 보류 중인 행 마지막 인출 되거나 업데이트 이후 현재 행에 대해 변경 내용을 전송 (사용 하 여 **업데이트** 또는 [UpdateAll](../../data/oledb/crowset-updateall.md)). 일반적으로 호출 [SetData](../../data/oledb/crowset-setdata.md) 한 행의에서 열에 데이터 값을 설정 하 여 호출 **업데이트** 이러한 변경 내용을 전송할 수 있습니다.  
  
 이 메서드를 사용 하려면 선택적 인터페이스 `IRowsetUpdate`, 모든 공급자에서 지원 되지 않는 있는;의 경우이 메서드는 반환 **E_NOINTERFACE**합니다. 설정 해야 **DBPROP_IRowsetUpdate** 를 `VARIANT_TRUE` 호출 하기 전에 **열려** 테이블이 나 행 집합을 포함 하는 명령입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [CRowset 클래스](../../data/oledb/crowset-class.md)   
 [IRowsetUpdate::Update](https://msdn.microsoft.com/en-us/library/ms719709.aspx)   
 [CRowset::UpdateAll](../../data/oledb/crowset-updateall.md)   
 [CRowset::SetData](../../data/oledb/crowset-setdata.md)