---
title: "CBulkRowset 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::CBulkRowset
- ATL.CBulkRowset
- ATL::CBulkRowset<TAccessor>
- CBulkRowset
- ATL.CBulkRowset<TAccessor>
dev_langs: C++
helpviewer_keywords: CBulkRowset class
ms.assetid: c6bde426-c543-4022-a98a-9519d9e2ae59
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 26ed8c0a3f58ae046ad3e4766b7e009023759be0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="cbulkrowset-class"></a>CBulkRowset 클래스
인출 하 고 한 번의 호출으로 여러 행 핸들을 검색 하 여 대량으로 데이터에서 작동 하도록 행을 조작 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
template <class TAccessor>  
class CBulkRowset : public CRowset<TAccessor>  
```  
  
#### <a name="parameters"></a>매개 변수  
 `TAccessor`  
 접근자 클래스입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="methods"></a>메서드  
  
|||  
|-|-|  
|[AddRefRows](../../data/oledb/cbulkrowset-addrefrows.md)|참조 횟수를 증가 시킵니다.|  
|[CBulkRowset](../../data/oledb/cbulkrowset-cbulkrowset.md)|생성자입니다.|  
|[MoveFirst](../../data/oledb/cbulkrowset-movefirst.md)|필요한 경우 새 대량 추출 실행과 데이터의 첫 번째 행을 검색 합니다.|  
|[MoveLast](../../data/oledb/cbulkrowset-movelast.md)|행을 마지막으로 이동합니다.|  
|[MoveNext](../../data/oledb/cbulkrowset-movenext.md)|데이터의 다음 행을 검색합니다.|  
|[MovePrev](../../data/oledb/cbulkrowset-moveprev.md)|이전 행으로 이동 합니다.|  
|[MoveToBookmark](../../data/oledb/cbulkrowset-movetobookmark.md)|이 책갈피에서 책갈피로 표시 행 이나 지정된 된 오프셋에 있는 행을 인출 합니다.|  
|[MoveToRatio](../../data/oledb/cbulkrowset-movetoratio.md)|행 집합의 소수 자릿수 위치에서 시작 하는 행을 인출 합니다.|  
|[ReleaseRows](../../data/oledb/cbulkrowset-releaserows.md)|현재 행을 설정 (**m_nCurrentRow**) 0 및 릴리스인 모든 행입니다.|  
|[SetRows](../../data/oledb/cbulkrowset-setrows.md)|한 번 호출 하 여 검색할 행 핸들의 수를 설정 합니다.|  
  
## <a name="example"></a>예  
 다음 예제에서는 사용 된 `CBulkRowset` 클래스입니다.  
  
 [!code-cpp[NVC_OLEDB_Consumer#1](../../data/oledb/codesnippet/cpp/cbulkrowset-class_1.cpp)]  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB 소비자 템플릿 참조](../../data/oledb/ole-db-consumer-templates-reference.md)