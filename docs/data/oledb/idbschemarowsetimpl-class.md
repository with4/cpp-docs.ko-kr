---
title: IDBSchemaRowsetImpl 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IDBSchemaRowsetImpl
dev_langs:
- C++
helpviewer_keywords:
- IDBSchemaRowsetImpl class
ms.assetid: bd7bf0d7-a1c6-4afa-88e3-cfdbdf560703
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: dc9da29bcd49b227596325913d521347b6b0ca0e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33110953"
---
# <a name="idbschemarowsetimpl-class"></a>IDBSchemaRowsetImpl 클래스
스키마 행 집합에 대한 구현을 제공합니다.  
  
## <a name="syntax"></a>구문

```cpp
template <class SessionClass>  
class ATL_NO_VTABLE IDBSchemaRowsetImpl : public IDBSchemaRowset  
```  
  
#### <a name="parameters"></a>매개 변수  
 `SessionClass`  
 `IDBSchemaRowsetImpl` 이 상속되는 클래스입니다. 일반적으로 이 클래스는 사용자의 세션 클래스가 됩니다.  
  
## <a name="members"></a>멤버  
  
### <a name="methods"></a>메서드  
  
|||  
|-|-|  
|[CheckRestrictions](../../data/oledb/idbschemarowsetimpl-checkrestrictions.md)|스키마 행 집합에 대해 제한의 유효성을 검사합니다.|  
|[CreateSchemaRowset](../../data/oledb/idbschemarowsetimpl-createschemarowset.md)|템플릿 매개 변수로 지정된 개체에 대한 COM 개체 작성자 함수를 구현합니다.|  
|[SetRestrictions](../../data/oledb/idbschemarowsetimpl-setrestrictions.md)|특정 스키마 행 집합에서 지원되는 제한을 지정합니다.|  
  
### <a name="interface-methods"></a>인터페이스 메서드  
  
|||  
|-|-|  
|[GetRowset](../../data/oledb/idbschemarowsetimpl-getrowset.md)|스키마 행 집합을 반환합니다.|  
|[GetSchemas](../../data/oledb/idbschemarowsetimpl-getschemas.md)|[IDBSchemaRowsetImpl::GetRowset](../../data/oledb/idbschemarowsetimpl-getrowset.md)에서 액세스할 수 있는 스키마 행 집합 목록을 반환합니다.|  
  
## <a name="remarks"></a>설명  
 이 클래스는 [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) 인터페이스 및 템플릿화된 작성자 함수 [CreateSchemaRowset](../../data/oledb/idbschemarowsetimpl-createschemarowset.md)를 구현합니다.  
  
 OLE DB는 스키마 행 집합을 사용하여 공급자의 데이터에 대한 데이터를 반환합니다. 이러한 데이터를 흔히 "메타데이터"라고 합니다. 기본적으로 공급자는 `DBSCHEMA_TABLES`OLE DB 프로그래머 참조 **의**IDBSchemaRowset **에 설명된 대로 항상**, [DBSCHEMA_COLUMNS](https://msdn.microsoft.com/en-us/library/ms713686.aspx) 및 *DBSCHEMA_PROVIDER_TYPES*를 지원해야 합니다. 스키마 행 집합은 스키마 맵에 지정됩니다. 스키마 맵 항목에 대한 자세한 내용은 [SCHEMA_ENTRY](../../data/oledb/schema-entry.md)를 참조하세요.  
  
 ATL 개체 마법사의 OLE DB 공급자 마법사는 프로젝트의 스키마 행 집합에 대한 코드를 자동으로 생성합니다. 기본적으로 마법사는 이전에 설명한 필수 스키마 행 집합을 지원합니다. ATL 개체 마법사를 사용하여 소비자를 만드는 경우 마법사는 스키마 행 집합을 사용하여 올바른 데이터를 공급자에 바인딩합니다. 올바른 메타데이터를 제공하는 스키마 행 집합을 구현하지 않은 경우 마법사는 올바른 데이터를 바인딩하지 않습니다.  
  
 공급자의 스키마 행 집합을 지원하는 방법에 대한 자세한 내용은 [스키마 행 집합 지원](../../data/oledb/supporting-schema-rowsets.md)을 참조하세요.  
  
 스키마 행 집합에 대한 자세한 내용은 [OLE DB 프로그래머 참조](https://msdn.microsoft.com/en-us/library/ms712921.aspx) 에서 *스키마 행 집합*을 참조하세요.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldb.h  
  
## <a name="see-also"></a>참고 항목  
 [IDBSchemaRowsetImpl 클래스 멤버](http://msdn.microsoft.com/en-us/e74f6f82-541c-42e7-b4c6-e2d4656a0649)   
 [스키마 행 집합 클래스 및 Typedef 클래스](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)   
 [스키마 행 집합 지원](../../data/oledb/supporting-schema-rowsets.md)