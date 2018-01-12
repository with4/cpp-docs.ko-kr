---
title: BEGIN_SCHEMA_MAP | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: BEGIN_SCHEMA_MAP
dev_langs: C++
helpviewer_keywords: BEGIN_SCHEMA_MAP macro
ms.assetid: 4e751023-35bc-4efd-9018-5448dd1ad751
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 9682ac8a31ec7c585b1da7b9bc14388413ba56fa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="beginschemamap"></a>BEGIN_SCHEMA_MAP
스키마 맵의 시작 부분을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      BEGIN_SCHEMA_MAP(  
   SchemaClass   
);  
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