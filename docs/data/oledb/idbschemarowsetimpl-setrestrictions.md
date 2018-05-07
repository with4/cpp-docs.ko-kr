---
title: 'Idbschemarowsetimpl:: Setrestrictions | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IDBSchemaRowsetImpl::SetRestrictions
- SetRestrictions
- IDBSchemaRowsetImpl.SetRestrictions
dev_langs:
- C++
helpviewer_keywords:
- SetRestrictions method
ms.assetid: 707d5065-b853-4d38-9b67-3066b4d3b279
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 8b6effd432b033941d404c4935cdbad5a2336ac8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="idbschemarowsetimplsetrestrictions"></a>IDBSchemaRowsetImpl::SetRestrictions
특정 스키마 행 집합에서 지원되는 제한을 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```
void SetRestrictions(ULONG cRestrictions,  
  GUID* /* rguidSchema */,  
   ULONG* rgRestrictions);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `cRestrictions`  
 [in] `rgRestrictions` 배열의 제한 수 및 `rguidSchema` 배열의 GUID 수입니다.  
  
 `rguidSchema`  
 [in] 제한을 페치할 스키마 행 집합의 GUID 배열입니다. 각 배열 요소는 스키마 행 집합 하나의 GUID를 포함합니다(예: `DBSCHEMA_TABLES`).  
  
 `rgRestrictions`  
 [in] 설정할 제한 값의 길이 `cRestrictions` 배열입니다. 각 요소는 GUID로 식별되는 스키마 행 집합에 대한 제한에 해당합니다. 공급자가 스키마 행 집합을 지원하지 않는 경우 요소는 0으로 설정됩니다. 그렇지 않은 경우에는 **ULONG** 값에 해당 스키마 행 집합에서 지원되는 제한을 나타내는 비트 마스크가 포함됩니다. 특정 스키마 행 집합에 해당 제한 사항에 자세한 내용은 스키마 행 집합 Guid의 표를 참조 하십시오.에 [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) 에 *OLE DB Programmer's Reference* 창에 SDK입니다.  
  
## <a name="remarks"></a>설명  
 **IDBSchemaRowset** 개체는 `SetRestrictions` 를 호출하여 특정 스키마 행 집합에서 지원되는 제한을 확인합니다(캐스팅되지 않은 포인터를 통해 [GetSchemas](../../data/oledb/idbschemarowsetimpl-getschemas.md) 에서 호출됨). 제한을 통해 소비자는 일치하는 행만 페치할 수 있습니다. 예를 들어 "MyTable" 테이블의 모든 열을 찾을 수 있습니다. 제한은 선택 사항이므로 지원되는 제한이 없는 경우(기본값) 항상 모든 데이터가 반환됩니다.  
  
 이 메서드의 기본 구현에서는 `rgRestrictions` 배열 요소를 0으로 설정입니다. 기본값 이외의 다른 제한을 설정하도록 세션 클래스의 기본값을 재정의합니다.  
  
 스키마 행 집합 지원 구현에 대한 자세한 내용은 [스키마 행 집합 지원](../../data/oledb/supporting-schema-rowsets.md)을 참조하세요.  
  
 스키마 행 집합을 지원하는 공급자에 대한 예제는 [UpdatePV](../../visual-cpp-samples.md) 샘플을 참조하세요.  
  
 스키마 행 집합에 대 한 자세한 내용은 참조 하십시오. [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) 에 *OLE DB Programmer's Reference* Windows sdk에서입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldb.h  
  
## <a name="see-also"></a>참고 항목  
 [IDBSchemaRowsetImpl 클래스](../../data/oledb/idbschemarowsetimpl-class.md)   
 [IDBSchemaRowsetImpl 클래스 멤버](http://msdn.microsoft.com/en-us/e74f6f82-541c-42e7-b4c6-e2d4656a0649)   
 [스키마 행 집합 클래스 및 Typedef 클래스](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)   
 [스키마 행 집합 지원](../../data/oledb/supporting-schema-rowsets.md)   
 [UpdatePV](../../visual-cpp-samples.md)