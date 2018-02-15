---
title: "IDBPropertiesImpl 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDBPropertiesImpl
- ATL.IDBPropertiesImpl
- ATL.IDBPropertiesImpl<T>
- ATL::IDBPropertiesImpl<T>
- ATL::IDBPropertiesImpl
dev_langs:
- C++
helpviewer_keywords:
- IDBPropertiesImpl class
ms.assetid: a7f15a8b-95b2-4316-b944-d5d03f8d74ab
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2cc488ac71afedaaf590ef93dbc8d43997e30d0c
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="idbpropertiesimpl-class"></a>IDBPropertiesImpl 클래스
에 대 한 구현을 제공는 `IDBProperties` 인터페이스입니다.  
  
## <a name="syntax"></a>구문

```cpp
template <class T>   
class ATL_NO_VTABLE IDBPropertiesImpl   
   : public IDBProperties, public CUtlProps<T>  
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 파생 된 클래스에 `IDBPropertiesImpl`합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="interface-methods"></a>인터페이스 메서드  
  
|||  
|-|-|  
|[GetProperties](../../data/oledb/idbpropertiesimpl-getproperties.md)|데이터 원본 개체 또는에 현재 설정 된 Initialization 속성 그룹에서 속성의 값에 대해 현재 설정 되어 있는 데이터 원본, 데이터 원본 정보 및 초기화 속성 그룹에서 속성의 값을 반환 합니다.는 열거자입니다.|  
|[GetPropertyInfo](../../data/oledb/idbpropertiesimpl-getpropertyinfo.md)|공급자가 지 원하는 모든 속성에 대 한 정보를 반환 합니다.|  
|[SetProperties](../../data/oledb/idbpropertiesimpl-setproperties.md)|열거자에 대 한 데이터 원본 개체에 대 한 데이터 원본 및 초기화 속성 그룹 또는 Initialization 속성 그룹의 속성을 설정 합니다.|  
  
## <a name="remarks"></a>설명  
 [IDBProperties](https://msdn.microsoft.com/en-us/library/ms719607.aspx) 데이터 원본 개체에 대 한 필수 인터페이스 이며 열거자에 대 한 선택적 인터페이스입니다. 그러나는 열거자를 노출 하는 경우 [IDBInitialize](https://msdn.microsoft.com/en-us/library/ms713706.aspx)를 노출 해야 `IDBProperties`합니다. `IDBPropertiesImpl` 구현 `IDBProperties` 정의 된 정적 함수를 사용 하 여 [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldb.h  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)