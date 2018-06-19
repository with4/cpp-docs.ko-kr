---
title: IColumnsInfoImpl 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.IColumnsInfoImpl<T>
- ATL::IColumnsInfoImpl
- IColumnsInfoImpl
- ATL.IColumnsInfoImpl
- ATL::IColumnsInfoImpl<T>
dev_langs:
- C++
helpviewer_keywords:
- IColumnsInfoImpl class
ms.assetid: ba74c1c5-2eda-4452-8b57-84919fa0d066
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 93cc4c44031d2091de64f2d82c1866135d1702cd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33101060"
---
# <a name="icolumnsinfoimpl-class"></a>IColumnsInfoImpl 클래스
구현을 제공는 [IColumnsInfo](https://msdn.microsoft.com/en-us/library/ms724541.aspx) 인터페이스입니다.  
  
## <a name="syntax"></a>구문

```cpp
template <class T>  
class ATL_NO_VTABLE IColumnsInfoImpl :   
   public IColumnsInfo,    
   public CDBIDOps  
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 파생 된 클래스에 `IColumnsInfoImpl`합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="methods"></a>메서드  
  
|||  
|-|-|  
|[GetColumnInfo](../../data/oledb/icolumnsinfoimpl-getcolumninfo.md)|대부분의 소비자에 필요한 열 메타 데이터를 반환 합니다.|  
|[MapColumnIDs](../../data/oledb/icolumnsinfoimpl-mapcolumnids.md)|지정된 된 열 Id로 식별 되는 행 집합에 있는 열의 서 수의 배열을 반환 합니다.|  
  
## <a name="remarks"></a>설명  
 행 집합 및 명령에 대해 필수 인터페이스입니다. 공급자의 동작을 수정 하려면 `IColumnsInfo` 공급자 열 맵을 수정 해야 하는 구현 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldb.h  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)