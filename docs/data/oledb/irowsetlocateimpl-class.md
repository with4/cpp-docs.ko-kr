---
title: "IRowsetLocateImpl 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IRowsetLocateImpl
dev_langs:
- C++
helpviewer_keywords:
- providers, bookmarks
- IRowsetLocateImpl class
- bookmarks, OLE DB
ms.assetid: a8aa3149-7ce8-4976-a680-2da193fd3234
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 27af767c9104159d6c398db226a5a45a36e01e2f
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="irowsetlocateimpl-class"></a>IRowsetLocateImpl 클래스
OLE DB 구현 [IRowsetLocate](https://msdn.microsoft.com/en-us/library/ms721190.aspx) 인터페이스에는 행 집합에서 임의의 행을 인출 합니다.  
  
## <a name="syntax"></a>구문

```cpp
template <  
   class T,   
   class RowsetInterface,   
   class RowClass = CSimpleRow,   
   class MapClass = CAtlMap < RowClass::KeyType, RowClass* >,   
   class BookmarkKeyType = LONG,   
   class BookmarkType = LONG,   
   class BookmarkMapClass = CAtlMap < RowClass::KeyType, RowClass* >>  
class ATL_NO_VTABLE IRowsetLocateImpl : public IRowsetImpl<  
       T,   
       RowsetInterface,   
       RowClass,   
       MapClass>  
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 클래스에서 파생 `IRowsetLocateImpl`합니다.  
  
 `RowsetInterface`  
 클래스에서 파생 `IRowsetImpl`합니다.  
  
 `RowClass`  
 에 대 한 저장소 단위는 **HROW**합니다.  
  
 `MapClass`  
 공급자가 보유 하는 모든 행 핸들에 대 한 저장소 단위입니다.  
  
 `BookmarkKeyType`  
 책갈피, LONG 또는 문자열 등의 형식입니다. 일반 책갈피 최소한 2 바이트의 길이 있어야 합니다. (OLE DB에 대 한 단일 바이트 길이 예약 되어 [표준 책갈피](https://msdn.microsoft.com/en-us/library/ms712954.aspx)**DBBMK_FIRST**, **DBBMK_LAST**, 및 **DBBMK_INVALID**.)  
  
 `BookmarkType`  
 책갈피-데이터 관계를 유지 관리 하기 위한 매핑 메커니즘입니다.  
  
 `BookmarkMapClass`  
 책갈피에서 보유 하는 모든 행 핸들에 대 한 저장소 단위입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="interface-methods"></a>인터페이스 메서드  
  
|||  
|-|-|  
|[Compare](../../data/oledb/irowsetlocateimpl-compare.md)|두 개의 책갈피를 비교합니다.|  
|[GetRowsAt](../../data/oledb/irowsetlocateimpl-getrowsat.md)|책갈피에서의 오프셋으로 지정 된 행부터 시작 하는 행을 인출 합니다.|  
|[GetRowsByBookmark](../../data/oledb/irowsetlocateimpl-getrowsbybookmark.md)|지정 된 책갈피를 일치 하는 행을 인출 합니다.|  
|[Hash](../../data/oledb/irowsetlocateimpl-hash.md)|지정 된 책갈피에 대 한 값을 해시 하는 반환 합니다.|  
  
### <a name="data-members"></a>데이터 멤버  
  
|||  
|-|-|  
|[m_rgBookmarks](../../data/oledb/irowsetlocateimpl-m-rgbookmarks.md)|책갈피의 배열입니다.|  
  
## <a name="remarks"></a>설명  
 `IRowsetLocateImpl` OLE DB 템플릿 구현인는 [IRowsetLocate](https://msdn.microsoft.com/en-us/library/ms721190.aspx) 인터페이스입니다. `IRowsetLocate` 행 집합에서 임의의 행을 인출 하는 데 사용 됩니다. 이 인터페이스를 구현 하지 않는 행 집합은 한 `sequential` 행 집합입니다. 때 `IRowsetLocate` 있으면 행 집합에 열 0이 행에 대 한 책갈피;이 열을 읽는 동일한 행에 위치를 변경 하는 데 사용할 수 있는 책갈피 값을 가져옵니다.  
  
 `IRowsetLocateImpl` 공급자의 책갈피 지원을 구현 하는 데 사용 됩니다. 책갈피는 자리 표시자 (인덱스 행 집합에서) 소비자는 행에 신속 하 게 반환할 수 있도록 하는 고속 데이터 액세스를 허용 합니다. 공급자 책갈피 수 있는 고유 하 게 결정 한 행을 식별 합니다. 사용 하 여 `IRowsetLocateImpl` 메서드, 책갈피를 비교할 수 있습니다, by 인출 행 오프셋, 책갈피에서 행 인출 및 책갈피에 대 한 해시 값을 반환 합니다.  
  
 행 집합에 OLE DB 책갈피를 지원 하려면이 클래스에서 상속 하는 행 집합을 확인 합니다.  
  
 책갈피 지원 구현에 대 한 자세한 내용은 참조 하십시오. [공급자의 책갈피 지원](../../data/oledb/provider-support-for-bookmarks.md) 에 *Visual c + + 프로그래머 가이드* 및 [책갈피](https://msdn.microsoft.com/en-us/library/ms709728.aspx) 는 에서*OLE DB Programmer's Reference* 플랫폼 SDK에에서 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더**: atldb.h  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)   
 [IRowsetLocate:IRowset](https://msdn.microsoft.com/en-us/library/ms721190.aspx)   
 [공급자의 책갈피 지원](../../data/oledb/provider-support-for-bookmarks.md)   
 [책갈피](https://msdn.microsoft.com/en-us/library/ms709728.aspx)