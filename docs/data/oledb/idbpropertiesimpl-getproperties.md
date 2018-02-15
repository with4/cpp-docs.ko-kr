---
title: 'Idbpropertiesimpl:: Getproperties | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDBPropertiesImpl::GetProperties
- IDBPropertiesImpl.GetProperties
- GetProperties
dev_langs:
- C++
helpviewer_keywords:
- GetProperties method
ms.assetid: ab24aebd-366d-49a1-b49b-bb46c6d90f05
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 576c5845e47c8dfaec715edb71f7325955d55222
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="idbpropertiesimplgetproperties"></a>IDBPropertiesImpl::GetProperties
데이터 원본 개체 또는에 현재 설정 된 Initialization 속성 그룹에서 속성의 값에 대해 현재 설정 되어 있는 데이터 원본, 데이터 원본 정보 및 초기화 속성 그룹에서 속성의 값을 반환 합니다.는 열거자입니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
      STDMETHOD(GetProperties)(ULONG cPropertySets,   
   const DBPROPIDSET rgPropertySets[],   
   ULONG * pcProperties,   
   DBPROPSET ** prgProperties);  
```  
  
#### <a name="parameters"></a>매개 변수  
 참조 [IDBProperties::GetProperties](https://msdn.microsoft.com/en-us/library/ms714344.aspx) 에 *OLE DB Programmer's Reference*합니다.  
  
 에 해당 하는 일부 매개 변수 *OLE DB Programmer's Reference* 매개 변수에서 설명 하는 다른 이름의 **IDBProperties::GetProperties**:  
  
|OLE DB 템플릿 매개 변수|*OLE DB Programmer's Reference* 매개 변수|  
|--------------------------------|------------------------------------------------|  
|`cPropertySets`|`cPropertyIDSets`|  
|`rgPropertySets`|`rgPropertyIDSets`|  
|*pcProperties*|*pcPropertySets*|  
|*prgProperties*|*prgPropertySets*|  
  
## <a name="remarks"></a>설명  
 이 메서드가 반환에서 속성의 값 공급자가 초기화 하는 경우는 **DBPROPSET_DATASOURCE**, **DBPROPSET_DATASOURCEINFO**, **DBPROPSET_DBINIT** 현재 데이터 원본 개체에 설정 된 속성 그룹입니다. 공급자 초기화 되지 않은 경우 반환 **DBPROPSET_DBINIT** 만 속성을 그룹화 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldb.h  
  
## <a name="see-also"></a>참고 항목  
 [IDBPropertiesImpl 클래스](../../data/oledb/idbpropertiesimpl-class.md)   
 [IDBPropertiesImpl::GetPropertyInfo](../../data/oledb/idbpropertiesimpl-getpropertyinfo.md)   
 [IDBPropertiesImpl::SetProperties](../../data/oledb/idbpropertiesimpl-setproperties.md)