---
title: IDBPropertiesImpl 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IDBPropertiesImpl
- ATL.IDBPropertiesImpl
- ATL.IDBPropertiesImpl<T>
- ATL::IDBPropertiesImpl<T>
- ATL::IDBPropertiesImpl
- IDBPropertiesImpl::GetProperties
- IDBPropertiesImpl.GetProperties
- GetProperties
- IDBPropertiesImpl::GetPropertyInfo
- IDBPropertiesImpl.GetPropertyInfo
- GetPropertyInfo
- IDBPropertiesImpl.SetProperties
- SetProperties
- IDBPropertiesImpl::SetProperties
dev_langs:
- C++
helpviewer_keywords:
- IDBPropertiesImpl class
- GetProperties method
- GetPropertyInfo method
- SetProperties method
ms.assetid: a7f15a8b-95b2-4316-b944-d5d03f8d74ab
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 3cc48b48c6d95cc07314030d6c7954898758e178
ms.sourcegitcommit: b0d6777cf4b580d093eaf6104d80a888706e7578
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/26/2018
ms.locfileid: "39269429"
---
# <a name="idbpropertiesimpl-class"></a>IDBPropertiesImpl 클래스
에 대 한 구현을 제공 합니다 `IDBProperties` 인터페이스입니다.  
  
## <a name="syntax"></a>구문

```cpp
template <class T>   
class ATL_NO_VTABLE IDBPropertiesImpl   
   : public IDBProperties, public CUtlProps<T>  
```  
  
### <a name="parameters"></a>매개 변수  
 *T*  
 클래스에서 파생 된 `IDBPropertiesImpl`합니다.  

## <a name="requirements"></a>요구 사항  
 **헤더:** atldb.h  
  
## <a name="members"></a>멤버  
  
### <a name="interface-methods"></a>인터페이스 메서드  
  
|||  
|-|-|  
|[GetProperties](#getproperties)|데이터 원본 개체의 초기화 속성 그룹에 현재 설정 된 속성의 값에 현재 설정 되어 있는 데이터 원본과 데이터 원본 정보를 초기화 속성 그룹의 속성 값을 반환 합니다 열거자입니다.|  
|[GetPropertyInfo](#getpropertyinfo)|공급자가 지 원하는 모든 속성에 대 한 정보를 반환 합니다.|  
|[SetProperties](#setproperties)|열거자에 대 한 데이터 원본 개체에 대 한 데이터 원본 및 초기화 속성 그룹 또는 초기화 속성 그룹의 속성을 설정합니다.|  
  
## <a name="remarks"></a>설명  
 [IDBProperties](https://msdn.microsoft.com/library/ms719607.aspx) 는 데이터 원본 개체에 대 한 필수 인터페이스 및 열거자에 대 한 선택적 인터페이스입니다. 그러나 열거자를 노출 하는 경우 [IDBInitialize](https://msdn.microsoft.com/library/ms713706.aspx)를 노출 해야 `IDBProperties`합니다. `IDBPropertiesImpl` 구현 `IDBProperties` 정의 된 정적 함수를 사용 하 여 [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md)합니다.  

## <a name="getproperties"></a> Idbpropertiesimpl:: Getproperties
데이터 원본 개체의 초기화 속성 그룹에 현재 설정 된 속성의 값에 현재 설정 되어 있는 데이터 원본과 데이터 원본 정보를 초기화 속성 그룹의 속성 값을 반환 합니다 열거자입니다.  
  
### <a name="syntax"></a>구문  
  
```cpp
      STDMETHOD(GetProperties)(ULONG cPropertySets,   
   const DBPROPIDSET rgPropertySets[],   
   ULONG * pcProperties,   
   DBPROPSET ** prgProperties);  
```  
  
#### <a name="parameters"></a>매개 변수  
 참조 [idbproperties:: Getproperties](https://msdn.microsoft.com/library/ms714344.aspx) 에 *OLE DB Programmer's Reference*합니다.  
  
 에 해당 하는 일부 매개 변수 *OLE DB Programmer's Reference* 매개 변수에서 설명 하는 다른 이름의 `IDBProperties::GetProperties`:  
  
|OLE DB 템플릿 매개 변수|*OLE DB Programmer's Reference* 매개 변수|  
|--------------------------------|------------------------------------------------|  
|*cPropertySets*|*cPropertyIDSets*|  
|*rgPropertySets*|*rgPropertyIDSets*|  
|*pcProperties*|*pcPropertySets*|  
|*prgProperties*|*prgPropertySets*|  
  
### <a name="remarks"></a>설명  
 이 메서드는 DBPROPSET_DATASOURCE DBPROPSET_DATASOURCEINFO, 속성의 값을 반환 공급자가 초기화 하는 경우 데이터 원본 개체의 현재 설정 되어 있는 DBPROPSET_DBINIT 속성 그룹입니다. 공급자 초기화 되지 않은 경우에 DBPROPSET_DBINIT 그룹 속성만 반환 합니다. 
  
## <a name="getpropertyinfo"></a> Idbpropertiesimpl:: Getpropertyinfo
데이터 원본에서 지 원하는 속성 정보를 반환 합니다.  
  
### <a name="syntax"></a>구문  
  
```cpp
      STDMETHOD(GetPropertyInfo)(ULONG cPropertySets,   
   const DBPROPIDSET rgPropertySets[],   
   ULONG * pcPropertyInfoSets,   
   DBPROPINFOSET ** prgPropertyInfoSets,   
   OLECHAR ** ppDescBuffer);  
```  
  
#### <a name="parameters"></a>매개 변수  
 참조 [idbproperties:: Getpropertyinfo](https://msdn.microsoft.com/library/ms718175.aspx) 에 *OLE DB Programmer's Reference*합니다.  
  
 에 해당 하는 일부 매개 변수 *OLE DB Programmer's Reference* 매개 변수에서 설명 하는 다른 이름의 `IDBProperties::GetPropertyInfo`:  
  
|OLE DB 템플릿 매개 변수|*OLE DB Programmer's Reference* 매개 변수|  
|--------------------------------|------------------------------------------------|  
|*cPropertySets*|*cPropertyIDSets*|  
|*rgPropertySets*|*rgPropertyIDSets*|  
  
### <a name="remarks"></a>설명  
 사용 하 여 [idbinitializeimpl:: M_pcutlpropinfo](../../data/oledb/idbinitializeimpl-m-pcutlpropinfo.md) 이 기능을 구현 합니다. 

## <a name="setproperties"></a> Idbpropertiesimpl:: Setproperties
열거자에 대 한 데이터 원본 개체에 대 한 데이터 원본 및 초기화 속성 그룹 또는 초기화 속성 그룹의 속성을 설정합니다.  
  
### <a name="syntax"></a>구문  
  
```cpp
      STDMETHOD(SetProperties)(ULONG cPropertySets,   
   DBPROPSET rgPropertySets[]);  
```  
  
#### <a name="parameters"></a>매개 변수  
 참조 [idbproperties:: Setproperties](https://msdn.microsoft.com/library/ms723049.aspx) 에 *OLE DB Programmer's Reference*합니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 DBPROPSET_DATASOURCE DBPROPSET_DATASOURCEINFO에 속성의 값을 설정 공급자가 초기화 하는 경우 데이터 원본 개체에 대 한 DBPROPSET_DBINIT 속성 그룹입니다. 공급자 초기화 되지 않은 경우에 DBPROPSET_DBINIT 그룹 속성만 설정 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)
