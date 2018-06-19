---
title: 'Idbschemarowsetimpl:: Getschemas | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::IDBSchemaRowsetImpl::GetSchemas
- GetSchemas
- IDBSchemaRowsetImpl<SessionClass>::GetSchemas
- ATL.IDBSchemaRowsetImpl.GetSchemas
- ATL::IDBSchemaRowsetImpl<SessionClass>::GetSchemas
- IDBSchemaRowsetImpl.GetSchemas
- IDBSchemaRowsetImpl::GetSchemas
dev_langs:
- C++
helpviewer_keywords:
- GetSchemas method
ms.assetid: fbe725a6-3acd-45f8-bcaf-10a6c1239cd2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 886b3ea82d8eb0193207438ce7c5a4fc51981cbc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33103309"
---
# <a name="idbschemarowsetimplgetschemas"></a>IDBSchemaRowsetImpl::GetSchemas
[IDBSchemaRowsetImpl::GetRowset](../../data/oledb/idbschemarowsetimpl-getrowset.md)에서 액세스할 수 있는 스키마 행 집합 목록을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
      STDMETHOD (GetSchema s )(ULONG * pcSchemas,  
   GUID ** prgSchemas,  
   ULONG** prgRest);  
```  
  
#### <a name="parameters"></a>매개 변수  
 *pcSchemas*  
 [out] 스키마 수로 채워진 **ULONG** 의 포인터입니다.  
  
 *prgSchemas*  
 [out] 스키마 행 집합 GUID 배열의 포인터로 채워진 GUID 배열의 포인터입니다.  
  
 *prgRest*  
 [out] 제한 배열로 채울 **ULONG**배열의 포인터입니다.  
  
## <a name="remarks"></a>설명  
 이 메서드는 공급자가 지원하는 모든 스키마 행 집합의 배열을 반환합니다. 참조 [idbschemarowset:: Getschemas](https://msdn.microsoft.com/en-us/library/ms719605.aspx) in the Windows SDK입니다.  
  
 이 함수를 구현하려면 사용자에게 세션 클래스의 스키마 맵이 있어야 합니다. 스키마 맵 정보를 사용하는 경우 맵의 스키마에 대한 GUID 배열로 응답합니다. 이는 공급자가 지원하는 스키마를 나타냅니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldb.h  
  
## <a name="see-also"></a>참고 항목  
 [IDBSchemaRowsetImpl 클래스](../../data/oledb/idbschemarowsetimpl-class.md)   
 [IDBSchemaRowsetImpl 클래스 멤버](http://msdn.microsoft.com/en-us/e74f6f82-541c-42e7-b4c6-e2d4656a0649)   
 [IDBSchemaRowsetImpl::GetRowset](../../data/oledb/idbschemarowsetimpl-getrowset.md)   
 [IDBSchemaRowset::GetRowset](https://msdn.microsoft.com/en-us/library/ms722634.aspx)   
 [스키마 행 집합 클래스 및 Typedef 클래스](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)