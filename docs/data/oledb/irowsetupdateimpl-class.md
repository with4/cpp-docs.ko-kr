---
title: IRowsetUpdateImpl 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IRowsetUpdateImpl
- ATL.IRowsetUpdateImpl
- ATL::IRowsetUpdateImpl
dev_langs:
- C++
helpviewer_keywords:
- providers, updatable
- IRowsetUpdateImpl class
- updatable providers, deferred update
ms.assetid: f85af76b-ab6f-4f8b-8f4a-337c9679d68f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 34efd252f67a0e3da9827ef97cff8bcab0a45532
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="irowsetupdateimpl-class"></a>IRowsetUpdateImpl 클래스
OLE DB 템플릿 구현의 [IRowsetUpdate](https://msdn.microsoft.com/en-us/library/ms714401.aspx) 인터페이스입니다.  
  
## <a name="syntax"></a>구문

```cpp
template <  
   class T,   
   class Storage,   
   class UpdateArray = CAtlArray<Storage>,   
   class RowClass = CSimpleRow,   
   class MapClass = CAtlMap <RowClass::KeyType, RowClass*>   
>  

class IRowsetUpdateImpl : public IRowsetChangeImpl<  
   T,   
   Storage,   
   IRowsetUpdate,   
   RowClass,   
   MapClass>  
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 클래스에서 파생 `IRowsetUpdateImpl`합니다.  
  
 `Storage`  
 사용자 레코드입니다.  
  
 `UpdateArray`  
 행 집합 업데이트에 대 한 캐시 된 데이터를 포함 하는 배열입니다.  
  
 `RowClass`  
 에 대 한 저장소 단위는 **HROW**합니다.  
  
 `MapClass`  
 공급자가 보유 하는 모든 행 핸들에 대 한 저장소 단위입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="interface-methods-used-with-irowsetchange"></a>인터페이스 메서드 (IRowsetChange와 함께 사용)  
  
|||  
|-|-|  
|[SetData](../../data/oledb/irowsetupdateimpl-setdata.md)|하나 이상의 열에 데이터 값을 설정합니다.|  
  
### <a name="interface-methods-used-with-irowsetupdate"></a>인터페이스 메서드 (IRowsetUpdate와 함께 사용)  
  
|||  
|-|-|  
|[GetOriginalData](../../data/oledb/irowsetupdateimpl-getoriginaldata.md)|가장 최근에 전송 또는 보류 중인 변경 내용을 무시 하 고 해당 데이터 원본에서 가져온 데이터를 가져옵니다.|  
|[GetPendingRows](../../data/oledb/irowsetupdateimpl-getpendingrows.md)|보류 중인 변경 내용이 있는 행 목록을 반환합니다.|  
|[GetRowStatus](../../data/oledb/irowsetupdateimpl-getrowstatus.md)|지정 된 행의 상태를 반환 합니다.|  
|[실행 취소](../../data/oledb/irowsetupdateimpl-undo.md)|마지막 페치 또는 업데이트 이후 행에 변경 내용을 실행 취소합니다.|  
|[업데이트](../../data/oledb/irowsetupdateimpl-update.md)|마지막 페치 또는 업데이트 이후 행에 대해 변경 내용을 전송 합니다.|  
  
### <a name="implementation-methods-callback"></a>구현 방법 (콜백)  
  
|||  
|-|-|  
|[IsUpdateAllowed](../../data/oledb/irowsetupdateimpl-isupdateallowed.md)|업데이트를 허용 하기 전에 등 보안을 무결성을 확인 하는 데 사용 합니다.|  
  
### <a name="data-members"></a>데이터 멤버  
  
|||  
|-|-|  
|[m_mapCachedData](../../data/oledb/irowsetupdateimpl-m-mapcacheddata.md)|지연 된 작업에 대 한 원래 데이터를 포함합니다.|  
  
## <a name="remarks"></a>설명  
 먼저 읽기 및에 대 한 설명서를 이해 해야 [IRowsetChange](https://msdn.microsoft.com/en-us/library/ms715790.aspx)적용 되기 때문에 있는 설명 된 모든 것도 여기, 합니다. 6 장 읽어야는 *OLE DB Programmer's Reference* 에 데이터를 설정 합니다.  
  
 `IRowsetUpdateImpl` OLE DB 구현 `IRowsetUpdate` 소비자가 변경 된 내용을 전송 지연 시킬 수 있는 인터페이스 `IRowsetChange` 에 데이터 소스 및 전송 하기 전에 변경 내용을 취소 합니다.  
  
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
 [업데이트 가능 공급자 만들기](../../data/oledb/creating-an-updatable-provider.md)