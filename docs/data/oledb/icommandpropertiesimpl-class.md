---
title: "ICommandPropertiesImpl 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ICommandPropertiesImpl
- ATL.ICommandPropertiesImpl
- ATL::ICommandPropertiesImpl
dev_langs:
- C++
helpviewer_keywords:
- ICommandPropertiesImpl class
ms.assetid: b3cf6aea-527e-4f0d-96e0-669178b021a2
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 36c524d8aae9223e47b39bfe6cbfdfafdaa006f6
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="icommandpropertiesimpl-class"></a>ICommandPropertiesImpl 클래스
구현을 제공는 [ICommandProperties](https://msdn.microsoft.com/en-us/library/ms723044.aspx) 인터페이스입니다.  
  
## <a name="syntax"></a>구문

```cpp
template <class T, class PropClass = T>  
class ATL_NO_VTABLE ICommandPropertiesImpl   
   : public ICommandProperties, public CUtlProps<PropClass>  
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 파생 클래스  
  
 `PropClass`  
 속성 클래스입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="interface-methods"></a>인터페이스 메서드  
  
|||  
|-|-|  
|[GetProperties](../../data/oledb/icommandpropertiesimpl-getproperties.md)|현재 행 집합에 대 한 요청 된 행 집합 속성 그룹의 속성 목록을 반환 합니다.|  
|[SetProperties](../../data/oledb/icommandpropertiesimpl-setproperties.md)|행 집합 속성 그룹의 속성을 설정합니다.|  
  
## <a name="remarks"></a>설명  
 명령에서 필수입니다. 정의 된 정적 함수에서 구현 되는 [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md) 매크로입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldb.h  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)