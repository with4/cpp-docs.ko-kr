---
title: IConvertTypeImpl 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.IConvertTypeImpl<T>
- IConvertTypeImpl
- ATL.IConvertTypeImpl
- ATL::IConvertTypeImpl
- ATL::IConvertTypeImpl<T>
dev_langs:
- C++
helpviewer_keywords:
- IConvertTypeImpl class
ms.assetid: 7f81e79e-7d3f-4cbe-b93c-d632a94b15f6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b9a8fdef3abf0c33fb6fca857086e6490ec959e9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33100046"
---
# <a name="iconverttypeimpl-class"></a>IConvertTypeImpl 클래스
구현을 제공는 [IConvertType](https://msdn.microsoft.com/en-us/library/ms715926.aspx) 인터페이스입니다.  
  
## <a name="syntax"></a>구문

```cpp
template <class T>  
class ATL_NO_VTABLE IConvertTypeImpl   
   : public IConvertType, public CConvertHelper  
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 파생 된 클래스에 `IConvertTypeImpl`합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="interface-methods"></a>인터페이스 메서드  
  
|||  
|-|-|  
|[CanConvert](../../data/oledb/iconverttypeimpl-canconvert.md)|명령에 또는 행 집합에서 형식 변환의 가용성에 대 한 정보를 제공합니다.|  
  
## <a name="remarks"></a>설명  
 이 인터페이스는 명령, 행 집합 및 인덱스 행 집합에 필수입니다. **IConvertTypeImpl** OLE DB에서 제공 된 변환 개체에 위임 하 여 인터페이스를 구현 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldb.h  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)