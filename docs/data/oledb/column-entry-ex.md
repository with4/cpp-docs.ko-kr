---
title: COLUMN_ENTRY_EX | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- COLUMN_ENTRY_EX
dev_langs:
- C++
helpviewer_keywords:
- COLUMN_ENTRY_EX macro
ms.assetid: dfad1b67-51c3-4289-b89a-da42d7e8bb88
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 843bb017bc575275c74f06f9bfc24973021f280b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="columnentryex"></a>COLUMN_ENTRY_EX
데이터베이스에서 특정 열에 대한 행 집합의 바인딩을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
COLUMN_ENTRY_EX(nOrdinal, wType, nLength, nPrecision, nScale, data, length, status)  
  
```  
  
#### <a name="parameters"></a>매개 변수  
 참조 [DBBINDING](https://msdn.microsoft.com/en-us/library/ms716845.aspx) 에 *OLE DB Programmer's Reference*합니다.  
  
 `nOrdinal`  
 [in] 열 번호입니다.  
  
 `wType`  
 [in] 데이터 형식입니다.  
  
 `nLength`  
 [in] 데이터 크기 (바이트)입니다.  
  
 `nPrecision`  
 [in] 데이터를 가져올 때 사용 하는 최대 전체 자릿수 및 `wType` 은 `DBTYPE_NUMERIC`합니다. 그렇지 않으면이 매개 변수는 무시 됩니다.  
  
 `nScale`  
 [in] 데이터를 가져올 때 사용할 소수 자릿수 및 `wType` 은 `DBTYPE_NUMERIC` 또는 **DBTYPE_DECIMAL**합니다.  
  
 `data`  
 [in] 사용자 레코드에서 해당 데이터 멤버입니다.  
  
 *length*  
 [in] 열 길이에 바인딩할 변수입니다.  
  
 *status*  
 [in] 열 상태에 바인딩할 변수입니다.  
  
## <a name="remarks"></a>설명  
 `COLUMN_ENTRY_EX` 매크로는 다음 위치에서 사용 됩니다.  
  
-   사이 [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) 및 [END_COLUMN_MAP](../../data/oledb/end-column-map.md) 매크로입니다.  
  
-   사이 [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) 및 [END_ACCESSOR](../../data/oledb/end-accessor.md) 매크로입니다.  
  
-   사이 [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md) 및 [END_PARAM_MAP](../../data/oledb/end-param-map.md) 매크로입니다.  
  
## <a name="example"></a>예제  
 참조 [BOOKMARK_ENTRY](../../data/oledb/bookmark-entry.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [매크로 및 전역 함수에 대 한 OLE DB 소비자 템플릿](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md)   
 [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md)   
 [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md)   
 [COLUMN_ENTRY](../../data/oledb/column-entry.md)   
 [COLUMN_ENTRY_PS](../../data/oledb/column-entry-ps.md)   
 [COLUMN_ENTRY_PS_LENGTH](../../data/oledb/column-entry-ps-length.md)   
 [COLUMN_ENTRY_LENGTH](../../data/oledb/column-entry-length.md)   
 [COLUMN_ENTRY_LENGTH_STATUS](../../data/oledb/column-entry-length-status.md)   
 [COLUMN_ENTRY_PS_LENGTH_STATUS](../../data/oledb/column-entry-ps-length-status.md)   
 [COLUMN_ENTRY_STATUS](../../data/oledb/column-entry-status.md)   
 [COLUMN_ENTRY_PS_STATUS](../../data/oledb/column-entry-ps-status.md)   
 [END_ACCESSOR](../../data/oledb/end-accessor.md)   
 [END_ACCESSOR_MAP](../../data/oledb/end-accessor-map.md)   
 [END_COLUMN_MAP](../../data/oledb/end-column-map.md)