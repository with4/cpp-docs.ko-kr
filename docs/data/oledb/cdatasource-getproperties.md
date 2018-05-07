---
title: 'Cdatasource:: Getproperties | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDataSource::GetProperties
- ATL.CDataSource.GetProperties
- CDataSource.GetProperties
- ATL::CDataSource::GetProperties
- GetProperties
dev_langs:
- C++
helpviewer_keywords:
- GetProperties method
ms.assetid: ffaecc17-9fe7-449e-94d6-43d31ad06cfc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e519504777a1ff9f2927d74340bec73e1b157e6d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="cdatasourcegetproperties"></a>CDataSource::GetProperties
연결 된 데이터 원본 개체에 대해 요청 된 속성 정보를 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```
HRESULT GetProperties(ULONG ulPropIDSets,   
   constDBPROPIDSET* pPropIDSet,   
   ULONG* pulPropertySets,   
   DBPROPSET** ppPropsets) const throw();  
```  
  
#### <a name="parameters"></a>매개 변수  
 참조 [IDBProperties::GetProperties](https://msdn.microsoft.com/en-us/library/ms714344.aspx) 에 *OLE DB Programmer's Reference* in the Windows SDK입니다.  
  
## <a name="return-value"></a>반환 값  
 표준 `HRESULT`입니다.  
  
## <a name="remarks"></a>설명  
 단일 속성을 사용 [GetProperty](../../data/oledb/cdatasource-getproperty.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [CDataSource 클래스](../../data/oledb/cdatasource-class.md)