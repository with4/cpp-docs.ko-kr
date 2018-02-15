---
title: 'Idbschemarowsetimpl:: Createschemarowset | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDBSchemaRowsetImpl::CreateSchemaRowset
- ATL::IDBSchemaRowsetImpl::CreateSchemaRowset
- CreateSchemaRowset
- IDBSchemaRowsetImpl.CreateSchemaRowset
- ATL.IDBSchemaRowsetImpl.CreateSchemaRowset
dev_langs:
- C++
helpviewer_keywords:
- CreateSchemaRowset method
ms.assetid: ad3e3e4d-45b9-461c-b7b8-3af6843631b1
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 4975f452844a9efc8002b661efa224bf7cac8a3f
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="idbschemarowsetimplcreateschemarowset"></a>IDBSchemaRowsetImpl::CreateSchemaRowset
템플릿 매개 변수로 지정된 개체에 대한 COM 개체 작성자 함수를 구현합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
template template <class SchemaRowsetClass>  
HRESULT CreateSchemaRowset(IUnknown *pUnkOuter,  
   ULONG cRestrictions,  
   const VARIANT rgRestrictions[],  
   REFIID riid,  
   ULONG cPropertySets,  
   DBPROPSET rgPropertySets[],  
   IUnknown** ppRowset,  
   SchemaRowsetClass*& pSchemaRowset);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pUnkOuter`  
 [in] 집계하는 경우 외부 [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) 이고, 그렇지 않으면 **NULL**입니다.  
  
 `cRestrictions`  
 [in] 스키마 행 집합에 적용된 제한 수입니다.  
  
 `rgRestrictions`  
 [in] 행 집합에 적용할 `cRestrictions`**VARIANT**배열입니다.  
  
 `riid`  
 [in] [IUnknown](../../atl/queryinterface.md) 출력에 대한 **QueryInterface**의 인터페이스입니다.  
  
 `cPropertySets`  
 [in] 설정할 속성 집합 수입니다.  
  
 `rgPropertySets`  
 [in] 설정할 속성을 지정하는 [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) 구조체의 배열입니다.  
  
 `ppRowset`  
 [out] **에서 요청된 나가는** IUnknown `riid`입니다. 이 **IUnknown** 은 스키마 행 집합 개체의 인터페이스입니다.  
  
 `pSchemaRowset`  
 [out] 스키마 행 집합 클래스의 인스턴스에 대한 포인터입니다. 일반적으로 이 매개 변수는 사용되지 않지만 COM 개체로 전달하기 전에 스키마 행 집합에서 추가 작업을 수행해야 하는 경우에 사용될 수 있습니다. `pSchemaRowset` 의 수명은 `ppRowset`에 의해 바인딩됩니다.  
  
## <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
## <a name="remarks"></a>설명  
 이 함수는 모든 형식의 스키마 행 집합에 대한 제네릭 작성자를 구현합니다. 일반적으로 사용자는 이 함수를 호출하지 않습니다. 스키마 맵 구현에 의해 호출됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldb.h  
  
## <a name="see-also"></a>참고 항목  
 [IDBSchemaRowsetImpl 클래스](../../data/oledb/idbschemarowsetimpl-class.md)   
 [IDBSchemaRowsetImpl 클래스 멤버](http://msdn.microsoft.com/en-us/e74f6f82-541c-42e7-b4c6-e2d4656a0649)   
 [SCHEMA_ENTRY](../../data/oledb/schema-entry.md)   
 [스키마 행 집합 클래스 및 Typedef 클래스](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)