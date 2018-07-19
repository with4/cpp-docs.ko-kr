---
title: CUtlProps 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CUtlProps
dev_langs:
- C++
helpviewer_keywords:
- CUtlProps class
ms.assetid: bb525178-765c-4e23-a110-c0fd70c05437
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 6b39edb002c254f5d122d574ac389c2fd4df8b38
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33101346"
---
# <a name="cutlprops-class"></a>CUtlProps 클래스
다양 한 OLE DB 속성 인터페이스에 대 한 속성 구현 (예를 들어 `IDBProperties`, `IDBProperties`, 및 `IRowsetInfo`).  
  
## <a name="syntax"></a>구문

```cpp
template < class T >  
class ATL_NO_VTABLE CUtlProps : public CUtlPropsBase  
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 포함 하는 클래스는 `BEGIN_PROPSET_MAP`합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="methods"></a>메서드  
  
|||  
|-|-|  
|[GetPropValue](../../data/oledb/cutlprops-getpropvalue.md)|속성 집합에서 속성을 가져옵니다.|  
|[IsValidValue](../../data/oledb/cutlprops-isvalidvalue.md)|값 속성을 설정 하기 전에 유효성을 검사 하는 데 사용 합니다.|  
|[OnInterfaceRequested](../../data/oledb/cutlprops-oninterfacerequested.md)|소비자 개체 생성 인터페이스에서 메서드를 호출 하는 경우 선택적 인터페이스에 대 한 요청을 처리 합니다.|  
|[OnPropertyChanged](../../data/oledb/cutlprops-onpropertychanged.md)|연결 된 속성을 처리 하는 속성을 설정한 후 호출 됩니다.|  
|[SetPropValue](../../data/oledb/cutlprops-setpropvalue.md)|속성 집합에는 속성을 설정합니다.|  
  
## <a name="remarks"></a>설명  
 이 클래스의 대부분에는 구현 정보입니다.  
  
 `CUtlProps` 내부적으로 속성을 설정 하기 위한 두 명의 구성원이 포함: [GetPropValue](../../data/oledb/cutlprops-getpropvalue.md) 및 [SetPropValue](../../data/oledb/cutlprops-setpropvalue.md)합니다.  
  
 속성 집합 맵에서 사용 되는 매크로에 대 한 자세한 내용은 참조 하십시오. [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md) 및 [END_PROPSET_MAP](../../data/oledb/end-propset-map.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldb.h  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)