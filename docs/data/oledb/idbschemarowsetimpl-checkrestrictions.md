---
title: 'Idbschemarowsetimpl:: Checkrestrictions | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CheckRestrictions
- IDBSchemaRowsetImpl::CheckRestrictions
- IDBSchemaRowsetImpl.CheckRestrictions
dev_langs:
- C++
helpviewer_keywords:
- CheckRestrictions method
ms.assetid: 3c9d77d2-0e4b-48fa-80db-d735da19f1cf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: c951c892a2e6d875fb1085b1d3208d43938347c1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="idbschemarowsetimplcheckrestrictions"></a>IDBSchemaRowsetImpl::CheckRestrictions
스키마 행 집합에 대해 제한의 유효성을 검사합니다.  
  
## <a name="syntax"></a>구문  
  
```
HRESULT CheckRestrictions(REFGUID rguidSchema,  
   ULONG cRestrictions,  const VARIANT rgRestrictions[]);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `rguidSchema`  
 [in] 요청된 스키마 행 집합 GUID에 대한 참조입니다(예: `DBSCHEMA_TABLES`).  
  
 `cRestrictions`  
 [in] 스키마 행 집합에 대해 소비자가 전달한 제한 수입니다.  
  
 `rgRestrictions`  
 [in] 설정할 제한 값의 길이 *cRestrictions* 배열입니다. 자세한 내용은 `rgRestrictions` SetRestrictions [에서](../../data/oledb/idbschemarowsetimpl-setrestrictions.md)매개 변수에 대한 설명을 참조하세요.  
  
## <a name="remarks"></a>설명  
 `CheckRestrictions` 를 사용하여 스키마 행 집합에 대해 제한의 유효성을 검사할 수 있습니다. 이 메서드는 `DBSCHEMA_TABLES`, **DBSCHEMA_COLUMNS**및 **DBSCHEMA_PROVIDER_TYPES** 스키마 행 집합에 대한 제한을 검사합니다. 이를 호출하여 **IDBSchemaRowset::GetRowset** 에 대한 소비자의 호출이 올바른지 확인할 수 있습니다. 위에 나열된 것과 다른 스키마 행 집합을 지원하려면 이 작업을 수행할 사용자 고유의 함수를 만들어야 합니다.  
  
 `CheckRestrictions` 는 소비자가 올바른 제한 및 공급자가 지원하는 올바른 제한 유형(예: 문자열의 경우 [)으로](../../data/oledb/idbschemarowsetimpl-getrowset.md) GetRowset `VT_BSTR` 를 호출하는지 확인합니다. 또한 올바른 개수의 제한이 지원되는지 확인합니다. 기본적으로 `CheckRestrictions` 는 [SetRestrictions](../../data/oledb/idbschemarowsetimpl-setrestrictions.md) 호출을 통해 지정된 행 집합에서 지원되는 제한을 공급자에 요청합니다. 그런 다음 공급자가 지원하는 제한과 소비자의 제한을 비교하여 성공 또는 실패를 반환합니다.  
  
 스키마 행 집합에 대 한 자세한 내용은 참조 하십시오. [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) 에 *OLE DB Programmer's Reference* Windows sdk에서입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldb.h  
  
## <a name="see-also"></a>참고 항목  
 [IDBSchemaRowsetImpl 클래스](../../data/oledb/idbschemarowsetimpl-class.md)   
 [IDBSchemaRowsetImpl 클래스 멤버](http://msdn.microsoft.com/en-us/e74f6f82-541c-42e7-b4c6-e2d4656a0649)   
 [스키마 행 집합 클래스 및 Typedef 클래스](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)