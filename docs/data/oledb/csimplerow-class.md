---
title: CSimpleRow 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CSimpleRow
- ATL::CSimpleRow
- ATL.CSimpleRow
dev_langs:
- C++
helpviewer_keywords:
- CSimpleRow class
ms.assetid: 06d9621d-60cc-4508-8b0c-528d1b1a809b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 68f1983eaad36494892c9a18dcb2dbebe2da1f11
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33099565"
---
# <a name="csimplerow-class"></a>CSimpleRow 클래스
에 사용 되는 행 핸들에 대 한 기본 구현을 제공는 [IRowsetImpl](../../data/oledb/irowsetimpl-class.md) 클래스입니다.  
  
## <a name="syntax"></a>구문

```cpp
class CSimpleRow  
```  
  
## <a name="members"></a>멤버  
  
### <a name="methods"></a>메서드  
  
|||  
|-|-|  
|[AddRefRow](../../data/oledb/csimplerow-addrefrow.md)|기존 행 핸들에 대 한 참조 횟수를 추가합니다.|  
|[Compare](../../data/oledb/csimplerow-compare.md)|같은 행 인스턴스를 참조 하는지 확인 하려면 두 개의 행을 비교 합니다.|  
|[CSimpleRow](../../data/oledb/csimplerow-csimplerow.md)|생성자입니다.|  
|[ReleaseRow](../../data/oledb/csimplerow-releaserow.md)|행을 해제합니다.|  
  
### <a name="data-members"></a>데이터 멤버  
  
|||  
|-|-|  
|[m_dwRef](../../data/oledb/csimplerow-m-dwref.md)|기존 행 핸들에 대 한 참조 횟수입니다.|  
|[m_iRowset](../../data/oledb/csimplerow-m-irowset.md)|커서를 나타내는 행 집합에는 인덱스입니다.|  
  
## <a name="remarks"></a>설명  
 행 핸들은 논리적으로 결과 행에 대 한 고유 태그입니다. `IRowsetImpl` 새 `CSimpleRow` 에서 요청 된 모든 행에 대 한 [irowsetimpl:: Getnextrows](../../data/oledb/irowsetimpl-getnextrows.md)합니다. `CSimpleRow` 에 대 한 기본 템플릿 인수 이므로 행 핸들의 고유한 구현을으로 대체할 수 있습니다 `IRowsetImpl`합니다. 이 클래스를 대체 하는 유일한 요구 사항은 형식의 단일 매개 변수를 허용 하는 생성자를 제공 하는 대체 클래스는 **긴**합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldb.h  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)   
 [IRowsetImpl 클래스](../../data/oledb/irowsetimpl-class.md)