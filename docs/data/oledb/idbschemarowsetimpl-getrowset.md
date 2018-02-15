---
title: 'Idbschemarowsetimpl:: Getrowset | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::IDBSchemaRowsetImpl::GetRowset
- ATL.IDBSchemaRowsetImpl.GetRowset
- IDBSchemaRowsetImpl<SessionClass>::GetRowset
- IDBSchemaRowsetImpl.GetRowset
- IDBSchemaRowsetImpl::GetRowset
- ATL::IDBSchemaRowsetImpl<SessionClass>::GetRowset
- GetRowset
dev_langs:
- C++
helpviewer_keywords:
- GetRowset method
ms.assetid: 3ae28c22-e186-4a15-8591-b0192e784a6f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: fb3e1460b4eee2de030397e05d527c219acb2bb9
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="idbschemarowsetimplgetrowset"></a>IDBSchemaRowsetImpl::GetRowset
스키마 행 집합을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
      STDMETHOD (GetRowset)(IUnknown *pUnkOuter,  
   REFGUID rguidSchema,  
   ULONG cRestrictions,  
   const VARIANT rgRestrictions[],  
   REFIID riid,  
   ULONG cPropertySets,  
   DBPROPSET rgPropertySets[],  
   IUnknown **ppRowset);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pUnkOuter`  
 [in] 집계하는 경우 외부 **IUnknown** 이고, 그렇지 않으면 **NULL**입니다.  
  
 `rguidSchema`  
 [in] 요청된 스키마 행 집합 GUID에 대한 참조입니다(예: `DBSCHEMA_TABLES`).  
  
 `cRestrictions`  
 [in] 행 집합에 적용할 제한 수입니다.  
  
 `rgRestrictions`  
 [in] 제한을 나타내는 `cRestrictions`**VARIANT**배열입니다.  
  
 `riid`  
 [in] 새로 만든 스키마 행 집합의 요청에 대한 IID입니다.  
  
 `cPropertySets`  
 [in] 설정할 속성 집합 수입니다.  
  
 `rgPropertySets`  
 [in/out] 새로 만든 스키마 행 집합에 설정할 [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) 구조체의 배열입니다.  
  
 `ppRowset`  
 [out] 새로 만든 스키마 행 집합에서 요청된 인터페이스에 대한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 이 메서드를 사용하려면 사용자에게 세션 클래스의 스키마 맵이 있어야 합니다. `GetRowset` 는 스키마 맵 정보를 사용하여 `rguidSchema` 매개 변수가 맵 항목 GUID 중 하나와 같은 경우 지정된 행 집합 개체를 만듭니다. 맵 항목에 대한 설명은 [SCHEMA_ENTRY](../../data/oledb/schema-entry.md) 를 참조하세요.  
  
 참조 [idbschemarowset:: Getrowset](https://msdn.microsoft.com/en-us/library/ms722634.aspx) in the Windows SDK입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldb.h  
  
## <a name="see-also"></a>참고 항목  
 [IDBSchemaRowsetImpl 클래스](../../data/oledb/idbschemarowsetimpl-class.md)   
 [IDBSchemaRowsetImpl 클래스 멤버](http://msdn.microsoft.com/en-us/e74f6f82-541c-42e7-b4c6-e2d4656a0649)   
 [IDBSchemaRowsetImpl::GetSchemas](../../data/oledb/idbschemarowsetimpl-getschemas.md)   
 [스키마 행 집합 클래스 및 Typedef 클래스](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)