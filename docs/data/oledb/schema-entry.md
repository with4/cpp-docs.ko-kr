---
title: SCHEMA_ENTRY | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- SCHEMA_ENTRY
dev_langs:
- C++
helpviewer_keywords:
- SCHEMA_ENTRY macro
ms.assetid: e8bee479-80f3-417e-8f41-cdaddd49690c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 665b337861959b28670a0b2e57649814853a7384
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="schemaentry"></a>SCHEMA_ENTRY
GUID는 클래스와 연결합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
      SCHEMA_ENTRY(guid,  
   rowsetClass);   
```  
  
#### <a name="parameters"></a>매개 변수  
 `guid`  
 스키마 행 집합 GUID입니다. 참조 [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) 에 *OLE DB Programmer's Reference* 스키마 행 집합 및 Guid 목록에 대 한 합니다.  
  
 *rowsetClass*  
 스키마 행 집합을 나타내기 위해 생성 되는 클래스입니다.  
  
## <a name="remarks"></a>설명  
 [IDBSchemaRowsetImpl](../../data/oledb/idbschemarowsetimpl-class.md) 그런 다음 지도 Guid, 목록에 대 한 쿼리 또는 GUID를 지정 하는 경우 행 집합을 만들 수 있습니다. 스키마 행 집합 `IDBSchemaRowsetImpl` 만듭니다 표준 비슷합니다 `CRowsetImpl`-파생 클래스를 제공 해야 하는 단 한 **Execute** 에 다음 서명이 메서드:  
  
```  
HRESULT Execute (LONG* pcRowsAffected,  
    ULONG cRestrictions,  
    const VARIANT* rgRestrictions);  
```  
  
 이 **Execute** 함수는 행 집합의 데이터를 채웁니다. 에 설명 된 대로 ATL 프로젝트 마법사 만듭니다 [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) 에 *OLE DB Programmer's Reference*, 프로젝트에서 스키마 행 집합의 각 3 개 필수 OLE DB 스키마에 대 한 초기 3:  
  
-   `DBSCHEMA_TABLES`  
  
-   **DBSCHEMA_COLUMNS**  
  
-   **DBSCHEMA_PROVIDER_TYPES**  
  
 마법사는 또한 스키마 맵에 해당 하는 세 가지 항목이 추가 합니다. 참조 [OLE DB 템플릿 공급자 만들기](../../data/oledb/creating-an-ole-db-provider.md) 공급자를 만들려면 마법사를 사용 하는 방법에 대 한 자세한 내용은 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldb.h  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 공급자 템플릿 매크로](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [BEGIN_SCHEMA_MAP](../../data/oledb/begin-schema-map.md)   
 [END_SCHEMA_MAP](../../data/oledb/end-schema-map.md)