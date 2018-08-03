---
title: IRowsetInfoImpl 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.IRowsetInfoImpl
- IRowsetInfoImpl
- ATL::IRowsetInfoImpl
- ATL.IRowsetInfoImpl.GetProperties
- IRowsetInfoImpl.GetProperties
- ATL::IRowsetInfoImpl::GetProperties
- IRowsetInfoImpl::GetProperties
- GetProperties
- ATL::IRowsetInfoImpl::GetReferencedRowset
- GetReferencedRowset
- ATL.IRowsetInfoImpl.GetReferencedRowset
- IRowsetInfoImpl.GetReferencedRowset
- IRowsetInfoImpl::GetReferencedRowset
- IRowsetInfoImpl::GetSpecification
- ATL.IRowsetInfoImpl.GetSpecification
- IRowsetInfoImpl.GetSpecification
- GetSpecification
- ATL::IRowsetInfoImpl::GetSpecification
dev_langs:
- C++
helpviewer_keywords:
- IRowsetInfoImpl class
- GetProperties method
- GetReferencedRowset method
- GetSpecification method
ms.assetid: 9c654155-7727-464e-bd31-143e68391a47
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f1f726459e72d57aa8e855df4f4f3ec5d566f687
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2018
ms.locfileid: "39337075"
---
# <a name="irowsetinfoimpl-class"></a>IRowsetInfoImpl 클래스
에 대 한 구현을 제공 합니다 [IRowsetInfo](https://msdn.microsoft.com/library/ms724541.aspx) 인터페이스입니다.  
  
## <a name="syntax"></a>구문

```cpp
template <class T, class PropClass = T>  
class ATL_NO_VTABLE IRowsetInfoImpl :   
   public IRowsetInfo,    
   public CUtlProps<PropClass>  
```  
  
### <a name="parameters"></a>매개 변수  
 *T*  
 클래스에서 파생 된 `IRowsetInfoImpl`합니다.  
  
 *PropClass*  
 기본적으로 사용자 정의 가능한 속성 클래스 *T*합니다. 

## <a name="requirements"></a>요구 사항  
 **헤더:** altdb.h   
  
## <a name="members"></a>멤버  
  
### <a name="interface-methods"></a>인터페이스 메서드  
  
|||  
|-|-|  
|[GetProperties](#getproperties)|행 집합에서 지 원하는 모든 속성의 현재 설정을 반환 합니다.|  
|[GetReferencedRowset](#getreferencedrowset)|책갈피 적용 되는 행 집합에 대 한 인터페이스 포인터를 반환 합니다.|  
|[GetSpecification](#getspecification)|이 행 집합을 만든 개체 (명령 또는 세션)에 대 한 인터페이스 포인터를 반환 합니다.|  
  
## <a name="remarks"></a>설명  
 행 집합에는 필수 인터페이스입니다. 이 클래스를 사용 하 여 행 집합 속성을 구현 합니다 [속성 집합 맵](../../data/oledb/begin-propset-map.md) 명령 클래스에 정의 합니다. 행 집합 클래스를 사용 하 여 명령 클래스의 속성 수를 설정 하는 나타나지만, 명령 또는 세션 개체로 만들 때 런타임 속성의 자체 복사본을 사용 하 여 행 집합 제공 됩니다.  
  
## <a name="getproperties"></a> Irowsetinfoimpl:: Getproperties
속성에 대 한 현재 설정을 반환 합니다 `DBPROPSET_ROWSET` 그룹입니다.  
  
### <a name="syntax"></a>구문  
  
```cpp
STDMETHOD (GetProperties )(const ULONG cPropertyIDSets,  
   const DBPROPIDSET rgPropertyIDSets[],  
   ULONG* pcPropertySets,  
   DBPROPSET** prgPropertySets);  
```  
  
#### <a name="parameters"></a>매개 변수  
 참조 [irowsetinfo:: Getproperties](https://msdn.microsoft.com/library/ms719611.aspx) 에 *OLE DB Programmer's Reference*합니다. 

## <a name="getreferencedrowset"></a> Irowsetinfoimpl:: Getreferencedrowset
책갈피 적용 되는 행 집합에 대 한 인터페이스 포인터를 반환 합니다.  
  
### <a name="syntax"></a>구문  
  
```cpp
STDMETHOD (GetReferencedRowset )(DBORDINAL iOrdinal,  
   REFIID riid,  
   IUnknown** ppReferencedRowset);  
```  
  
#### <a name="parameters"></a>매개 변수  
 참조 [IRowsetInfo::GetReferencedRowset](https://msdn.microsoft.com/library/ms721145.aspx) 에 *OLE DB Programmer's Reference*합니다. 합니다 *iOrdinal* 매개 변수는 책갈피 열 이어야 합니다. 

## <a name="getspecification"></a> Irowsetinfoimpl:: Getspecification
이 행 집합을 만든 개체 (명령 또는 세션)에 대 한 인터페이스 포인터를 반환 합니다.  
  
### <a name="syntax"></a>구문  
  
```cpp
STDMETHOD (GetSpecification )(REFIID riid,  
   IUnknown** ppSpecification);  
```  
  
#### <a name="parameters"></a>매개 변수  
 참조 [IRowsetInfo::GetSpecification](https://msdn.microsoft.com/library/ms716746.aspx) 에 *OLE DB Programmer's Reference*합니다.  
  
### <a name="remarks"></a>설명  
 이 메서드를 사용 하 여 [IGetDataSourceImpl](../../data/oledb/igetdatasourceimpl-class.md) 데이터 원본 개체에서 속성을 검색할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)