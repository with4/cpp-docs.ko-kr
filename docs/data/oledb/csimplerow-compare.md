---
title: 'Csimplerow:: Compare | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CSimpleRow.Compare
- CSimpleRow::Compare
dev_langs:
- C++
helpviewer_keywords:
- Compare method
ms.assetid: 0bb65f09-c7bc-449b-aa4e-c828cac13510
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 75d79e753f1f4af630c26ef07fbb7241576535ce
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33098967"
---
# <a name="csimplerowcompare"></a>CSimpleRow::Compare
같은 행 인스턴스를 참조 하는지 확인 하려면 두 개의 행을 비교 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT Compare(CSimpleRow* pRow);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pRow`  
 에 대 한 포인터는 `CSimpleRow` 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 `HRESULT` 값을 일반적으로 `S_OK`, 두 개의 행이 같은 행 인스턴스를 나타내는 또는 **S_FALSE**, 다르면 두 개의 행을 나타내는입니다. 참조 [IRowsetIdentity::IsSameRow](https://msdn.microsoft.com/en-us/library/ms719629.aspx) 에 *OLE DB Programmer's Reference* 다른 가능한 반환 값에 대 한 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldb.h  
  
## <a name="see-also"></a>참고 항목  
 [CSimpleRow 클래스](../../data/oledb/csimplerow-class.md)   
 [CSimpleRow::ReleaseRow](../../data/oledb/csimplerow-releaserow.md)   
 [IRowsetImpl::RefRows](../../data/oledb/irowsetimpl-refrows.md)