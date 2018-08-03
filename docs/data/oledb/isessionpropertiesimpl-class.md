---
title: ISessionPropertiesImpl 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ISessionPropertiesImpl
- ISessionPropertiesImpl::GetProperties
- ISessionPropertiesImpl.GetProperties
- GetProperties
- ISessionPropertiesImpl.SetProperties
- SetProperties
- ISessionPropertiesImpl::SetProperties
dev_langs:
- C++
helpviewer_keywords:
- ISessionPropertiesImpl class
- GetProperties method
- SetProperties method
ms.assetid: ca0ba254-c7dc-4c52-abec-cf895a0c6a63
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 5da668814888c11c5aaa0734be5ebc39b943778e
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2018
ms.locfileid: "39337257"
---
# <a name="isessionpropertiesimpl-class"></a>ISessionPropertiesImpl 클래스
구현을 제공 합니다 [ISessionProperties](https://msdn.microsoft.com/library/ms713721.aspx) 인터페이스입니다.  
  
## <a name="syntax"></a>구문

```cpp
template <class T, class PropClass = T>  
class ATL_NO_VTABLE ISessionPropertiesImpl :  
   public ISessionProperties,    
   public CUtlProps<PropClass>  
```  
  
### <a name="parameters"></a>매개 변수  
 *T*  
 클래스에서 파생 된 `ISessionPropertiesImpl`합니다.  
  
 *PropClass*  
 기본적으로 사용자 정의 가능한 속성 클래스 *T*합니다.  

## <a name="requirements"></a>요구 사항  
 **헤더:** atldb.h  
  
## <a name="members"></a>멤버  
  
### <a name="interface-methods"></a>인터페이스 메서드  
  
|||  
|-|-|  
|[GetProperties](#getproperties)|현재 세션에 설정 된 세션 속성 그룹의 속성 목록을 반환 합니다.|  
|[SetProperties](#setproperties)|세션 속성 그룹의 속성을 설정합니다.|  
  
## <a name="remarks"></a>설명  
 세션에서 필수 인터페이스입니다. 이 클래스는 정의 된 정적 함수를 호출 하 여 세션 속성을 구현 합니다 [속성 집합 맵](../../data/oledb/begin-propset-map.md)합니다. 세션 클래스의 속성 집합 지도 지정 해야 합니다.  
  
## <a name="getproperties"></a> Isessionpropertiesimpl:: Getproperties
속성의 목록을 반환 합니다 `DBPROPSET_SESSION` 현재 세션에 설정 된 속성 그룹입니다.  
  
### <a name="syntax"></a>구문  
  
```cpp
STDMETHOD(GetProperties)(ULONG cPropertyIDSets,   
   const DBPROPIDSET rgPropertyIDSets[],   
   ULONG * pcPropertySets,   
   DBPROPSET ** prgPropertySets);  
```  
  
#### <a name="parameters"></a>매개 변수  
 참조 [ISessionProperties::GetProperties](https://msdn.microsoft.com/library/ms723643.aspx) 에 *OLE DB Programmer's Reference*합니다. 

## <a name="setproperties"></a> Isessionpropertiesimpl:: Setproperties
속성을 설정 합니다 `DBPROPSET_SESSION` 속성 그룹입니다.  
  
### <a name="syntax"></a>구문  
  
```cpp
STDMETHOD(SetProperties)(ULONG cPropertySets,   
   DBPROPSET rgPropertySets[]);  
```  
  
#### <a name="parameters"></a>매개 변수  
 참조 [ISessionProperties::SetProperties](https://msdn.microsoft.com/library/ms714405.aspx) 에 *OLE DB Programmer's Reference*합니다.  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)