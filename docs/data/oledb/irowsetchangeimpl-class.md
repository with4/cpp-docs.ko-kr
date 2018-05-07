---
title: IRowsetChangeImpl 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::IRowsetChangeImpl
- IRowsetChangeImpl
- ATL.IRowsetChangeImpl
dev_langs:
- C++
helpviewer_keywords:
- providers, updatable
- updatable providers, immediate update
- IRowsetChangeImpl class
ms.assetid: 1e9fee15-ed9e-4387-af8f-215569beca6c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 11435cd1372147efb14aed78448d889fd60dc5a0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="irowsetchangeimpl-class"></a>IRowsetChangeImpl 클래스
OLE DB 템플릿 구현의 [IRowsetChange](https://msdn.microsoft.com/en-us/library/ms715790.aspx) OLE DB 사양에 대 한 인터페이스입니다.  
  
## <a name="syntax"></a>구문

```cpp
template <  
   class T,   
   class Storage,   
   class BaseInterface = IRowsetChange,   
   class RowClass = CSimpleRow,   
   class MapClass = CAtlMap <RowClass::KeyType, RowClass*>>  
class ATL_NO_VTABLE IRowsetChangeImpl : public BaseInterface  
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 클래스에서 파생 `IRowsetChangeImpl`합니다.  
  
 `Storage`  
 사용자 레코드입니다.  
  
 `BaseInterface`  
 기본 클래스는 인터페이스에 대 한 같은 `IRowsetChange`합니다.  
  
 `RowClass`  
 행 핸들에 대 한 저장소 단위입니다.  
  
 `MapClass`  
 공급자가 보유 하는 모든 행 핸들에 대 한 저장소 단위입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="interface-methods-used-with-irowsetchange"></a>인터페이스 메서드 (IRowsetChange와 함께 사용)  
  
|||  
|-|-|  
|[DeleteRows](../../data/oledb/irowsetchangeimpl-deleterows.md)|행 집합에서 행을 삭제합니다.|  
|[InsertRow](../../data/oledb/irowsetchangeimpl-insertrow.md)|행 집합에 행을 삽입 합니다.|  
|[SetData](../../data/oledb/irowsetchangeimpl-setdata.md)|하나 이상의 열에 데이터 값을 설정합니다.|  
  
### <a name="implementation-method-callback"></a>구현 메서드 (콜백)  
  
|||  
|-|-|  
|[FlushData](../../data/oledb/irowsetchangeimpl-flushdata.md)|데이터 저장소에 커밋하는 공급자에 의해 재정의 되 면입니다.|  
  
## <a name="remarks"></a>설명  
 이 인터페이스는 데이터 저장소에 즉시 쓰기 작업을 담당 합니다. "즉시" 의미는 최종 사용자 (소비자를 사용 하 여 person)를 모두 변경 하면 해당 변경 내용이 즉시 전송 됩니다 데이터 저장 (하 고은 취소할 수 없습니다).  
  
 `IRowsetChangeImpl` OLE DB 구현 `IRowsetChange` 행을 삭제 하 고 새 행을 삽입의 기존 행의 열 값의 업데이트 수 있도록 하는 인터페이스입니다.  
  
 OLE DB 템플릿 구현은 모든 기본 메서드를 지원 (`SetData`, `InsertRow`, 및 `DeleteRows`).  
  
> [!IMPORTANT]
>  공급자를 구현 하기 전에 다음 문서를 읽는 것이 가장 좋습니다.  
  
-   [업데이트 가능 공급자 만들기](../../data/oledb/creating-an-updatable-provider.md)  
  
-   6 장은 *OLE DB 프로그래머 참조*  
  
-   또한 참조 방법을 `RUpdateRowset` 클래스는 UpdatePV 샘플에서 사용  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldb.h  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)