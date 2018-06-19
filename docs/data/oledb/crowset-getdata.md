---
title: 'Crowset:: Getdata | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CRowset<TAccessor>::GetData
- ATL::CRowset<TAccessor>::GetData
- ATL::CRowset::GetData
- ATL.CRowset<TAccessor>.GetData
- CRowset<TAccessor>.GetData
- CRowset::GetData
- CRowset.GetData
- ATL.CRowset.GetData
dev_langs:
- C++
helpviewer_keywords:
- GetData method [OLE DB]
ms.assetid: 1e0347b5-3e24-4ff8-a790-839616c1522f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: c0a8268f115f6c6d5a887bea7aad8a244d7e530c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33096446"
---
# <a name="crowsetgetdata"></a>CRowset::GetData
행의 행 집합의 복사본에서 데이터를 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT GetData() throw();   


HRESULT GetData(int nAccessor) throw();  
```  
  
#### <a name="parameters"></a>매개 변수  
 `nAccessor`  
 [in] \(0 오프셋) 인덱스 데이터에 액세스 하기 위해 사용 하는 접근자 수입니다.  
  
## <a name="return-value"></a>반환 값  
 표준 `HRESULT`입니다.  
  
## <a name="remarks"></a>설명  
 자동에 없는 접근자를 지정 하는 경우 [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md),이 메서드를 사용 하 여 명시적으로 접근자 번호를 전달 하 여 데이터를 가져옵니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [CRowset 클래스](../../data/oledb/crowset-class.md)