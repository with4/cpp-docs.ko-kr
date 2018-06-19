---
title: BEGIN_SCHEMA_MAP | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- BEGIN_SCHEMA_MAP
dev_langs:
- C++
helpviewer_keywords:
- BEGIN_SCHEMA_MAP macro
ms.assetid: 4e751023-35bc-4efd-9018-5448dd1ad751
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 36839996a95257d39ded740c431f9db6ed2b372d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33095484"
---
# <a name="beginschemamap"></a>BEGIN_SCHEMA_MAP
스키마 맵의 시작 부분을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
      BEGIN_SCHEMA_MAP(SchemaClass);  
```  
  
#### <a name="parameters"></a>매개 변수  
 *SchemaClass*  
 해당 맵을 포함 하는 클래스입니다. 일반적으로이 세션 클래스 됩니다.  
  
## <a name="remarks"></a>설명  
 참조 [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) 스키마 행 집합에 대 한 자세한 내용은 Windows sdk입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldb.h  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 공급자 템플릿 매크로](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [SCHEMA_ENTRY](../../data/oledb/schema-entry.md)   
 [END_SCHEMA_MAP](../../data/oledb/end-schema-map.md)   
 [IDBSchemaRowsetImpl 클래스](../../data/oledb/idbschemarowsetimpl-class.md)