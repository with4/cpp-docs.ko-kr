---
title: "IRowsetImpl 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IRowsetImpl
dev_langs: C++
helpviewer_keywords: IRowsetImpl class
ms.assetid: 6a9189af-7556-45b1-adcb-9d62bb36704c
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7b4d8dd6f6dced2b4847939b0d7ed560f1d59479
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="irowsetimpl-class"></a>IRowsetImpl 클래스
`IRowset` 인터페이스의 구현을 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```  
template <  
   class T,   
   class RowsetInterface,  
   class RowClass = CSimpleRow,  
   class MapClass = CAtlMap <  
      RowClass::KeyType,  
      RowClass*   
   >  
>  
class ATL_NO_VTABLE IRowsetImpl : public RowsetInterface  
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 파생 된 클래스에 `IRowsetImpl`합니다.  
  
 `RowsetInterface`  
 클래스에서 파생 `IRowsetImpl`합니다.  
  
 `RowClass`  
 에 대 한 저장소 단위는 **HROW**합니다.  
  
 `MapClass`  
 공급자가 보유 하는 모든 행 핸들에 대 한 저장소 단위입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="methods"></a>메서드  
  
|||  
|-|-|  
|[AddRefRows](../../data/oledb/irowsetimpl-addrefrows.md)|기존 행 핸들에 대 한 참조 횟수를 추가합니다.|  
|[CreateRow](../../data/oledb/irowsetimpl-createrow.md)|에 의해 호출 [GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md) 할당할 새 **HROW**합니다. 사용자가 직접 호출 되지 않습니다.|  
|[GetData](../../data/oledb/irowsetimpl-getdata.md)|행의 행 집합의 복사본에서 데이터를 검색합니다.|  
|[GetDBStatus](../../data/oledb/irowsetimpl-getdbstatus.md)|지정된 된 필드에 대 한 상태를 반환합니다.|  
|[GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md)|행을 순차적으로 인출에서 이전 위치로 기억|  
|[IRowsetImpl](../../data/oledb/irowsetimpl-class.md)|생성자입니다. 사용자가 직접 호출 되지 않습니다.|  
|[RefRows](../../data/oledb/irowsetimpl-refrows.md)|에 의해 호출 [AddRefRows](../../data/oledb/irowsetimpl-addrefrows.md) 및 [ReleaseRows](../../data/oledb/irowsetimpl-releaserows.md)합니다. 사용자가 직접 호출 되지 않습니다.|  
|[ReleaseRows](../../data/oledb/irowsetimpl-releaserows.md)|행을 해제합니다.|  
|[Restartposition이](../../data/oledb/irowsetimpl-restartposition.md)|다음 인출 위치를 초기 위치로; 위치 변경 즉, 행 집합을 첫 번째 경우에 해당 위치에 만들어집니다.|  
|[SetDBStatus](../../data/oledb/irowsetimpl-setdbstatus.md)|지정된 된 필드에 대 한 상태 플래그를 설정합니다.|  
  
### <a name="data-members"></a>데이터 멤버  
  
|||  
|-|-|  
|[m_bCanFetchBack](../../data/oledb/irowsetimpl-m-bcanfetchback.md)|공급자는 이전 버전과 인출 지원 하는지 여부를 나타냅니다.|  
|[m_bCanScrollBack](../../data/oledb/irowsetimpl-m-bcanscrollback.md)|공급자는 커서 스크롤을 이전 버전과 가질 수 있는지 여부를 나타냅니다.|  
|[m_bReset](../../data/oledb/irowsetimpl-m-breset.md)|공급자가 해당 커서 위치를 다시 설정 하는지 여부를 나타냅니다. 이 뒤로 스크롤 또는 뒤로 인출 하는 경우 특별 한 의미 [GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md)합니다.|  
|[m_iRowset](../../data/oledb/irowsetimpl-m-irowset.md)|커서를 나타내는 행 집합에는 인덱스입니다.|  
|[m_rgRowHandles](../../data/oledb/irowsetimpl-m-rgrowhandles.md)|목록 행 핸들입니다.|  
  
## <a name="remarks"></a>설명  
 [IRowset](https://msdn.microsoft.com/en-us/library/ms720986.aspx) 기본 행 집합 인터페이스입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldb.h  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)