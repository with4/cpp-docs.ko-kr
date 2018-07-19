---
title: IRowsetIdentityImpl 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::IRowsetIdentityImpl
- ATL.IRowsetIdentityImpl
- IRowsetIdentityImpl
dev_langs:
- C++
helpviewer_keywords:
- IRowsetIdentityImpl class
ms.assetid: 56821edf-e045-40c8-96bd-231552cd5799
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 29ec88546a622ee42ce0e81efa9400305e2e14ae
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33101424"
---
# <a name="irowsetidentityimpl-class"></a>IRowsetIdentityImpl 클래스
OLE DB 구현 [IRowsetIdentity](https://msdn.microsoft.com/en-us/library/ms715913.aspx) 행 id에 대 한 테스트 수 있도록 하는 인터페이스입니다.  
  
## <a name="syntax"></a>구문

```cpp
template <class T, class RowClass = CSimpleRow>  
class ATL_NO_VTABLE IRowsetIdentityImpl   
   : public IRowsetIdentity  
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 클래스에서 파생 `IRowsetIdentityImpl`합니다.  
  
 `RowClass`  
 에 대 한 저장소 단위는 **HROW**합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="methods"></a>메서드  
  
|||  
|-|-|  
|[IsSameRow](../../data/oledb/irowsetidentityimpl-issamerow.md)|동일한 행을 참조 하는 경우를 확인 하려면 두 개의 행 핸들을 비교 합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldb.h  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)