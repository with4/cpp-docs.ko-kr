---
title: 'Cdbpropset:: Setguid | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.CDBPropSet.SetGUID
- CDBPropSet.SetGUID
- ATL::CDBPropSet::SetGUID
- SetGUID
- CDBPropSet::SetGUID
dev_langs:
- C++
helpviewer_keywords:
- SetGUID method
- AddProperty method
ms.assetid: a4cce036-cf1f-4897-9712-7b01eaf887ff
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 140bc76968780efff826ccc42343f27b2cd2eae6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="cdbpropsetsetguid"></a>CDBPropSet::SetGUID
설정의 **guidPropertySet** 필드에 **DBPROPSET** 구조입니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
      void SetGUID(const GUID& guid) throw();  
```  
  
#### <a name="parameters"></a>매개 변수  
 `guid`  
 [in] 설정 하는 데 GUID는 **guidPropertySet** 필드는 [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) 구조입니다.  
  
## <a name="remarks"></a>설명  
 이 필드를 설정할 수 있습니다는 [생성자](../../data/oledb/cdbpropset-cdbpropset.md) 도 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [CDBPropSet 클래스](../../data/oledb/cdbpropset-class.md)