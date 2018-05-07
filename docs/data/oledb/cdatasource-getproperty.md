---
title: 'Cdatasource:: Getproperty | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::CDataSource::GetProperty
- ATL.CDataSource.GetProperty
- CDataSource.GetProperty
- CDataSource::GetProperty
dev_langs:
- C++
helpviewer_keywords:
- GetProperty method
ms.assetid: 6531147c-b164-4ab5-a4a7-509634b85b4d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: afe21f6f41491a4f62eda09e2df43aa470417e20
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="cdatasourcegetproperty"></a>CDataSource::GetProperty
연결 된 데이터 원본 개체에 대해 지정된 된 속성의 값을 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT GetProperty(const GUID& guid,   
   DBPROPID propid,   
   VARIANT* pVariant) const throw();  
```  
  
#### <a name="parameters"></a>매개 변수  
 `guid`  
 [in] 반환할 속성에 대해 설정할 속성을 식별 하는 GUID입니다.  
  
 `propid`  
 [in] ID 속성에 대해 반환할 속성입니다.  
  
 *pVariant*  
 [out] Variant에 대 한 포인터를 **GetProperty** 속성의 값을 반환 합니다.  
  
## <a name="return-value"></a>반환 값  
 표준 `HRESULT`입니다.  
  
## <a name="remarks"></a>설명  
 여러 속성을 사용 [GetProperties](../../data/oledb/cdatasource-getproperties.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [CDataSource 클래스](../../data/oledb/cdatasource-class.md)