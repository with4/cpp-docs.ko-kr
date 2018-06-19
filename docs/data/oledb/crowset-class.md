---
title: CRowset 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.CRowset<TAccessor>
- CRowset
- ATL::CRowset
- ATL::CRowset<TAccessor>
- ATL.CRowset
dev_langs:
- C++
helpviewer_keywords:
- CRowset class
ms.assetid: b0228a90-b8dd-47cc-b397-8d4c15c1e7f4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 5c9a23c2e879f0d2fe1add1a970c64f6fbcc27b2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33098578"
---
# <a name="crowset-class"></a>CRowset 클래스
OLE DB 행 집합 개체와 관련 된 몇 가지 캡슐화 인터페이스를 만들고 행 집합 데이터 조작 메서드를 제공 합니다.  
  
## <a name="syntax"></a>구문

```cpp
template <class TAccessor = CAccessorBase>  
class CRowset  
```  
  
#### <a name="parameters"></a>매개 변수  
 `TAccessor`  
 접근자 클래스입니다. 기본값은 `CAccessorBase`입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="methods"></a>메서드  
  
|||  
|-|-|  
|[AddRefRows](../../data/oledb/crowset-addrefrows.md)|현재 행과 연결 된 참조 횟수를 증가 합니다.|  
|[닫기](../../data/oledb/crowset-close.md)|행과 현재 해제 `IRowset` 인터페이스입니다.|  
|[Compare](../../data/oledb/crowset-compare.md)|사용 하 여 책갈피 비교 하 여 두 개의 [IRowsetLocate::Compare](https://msdn.microsoft.com/en-us/library/ms709539.aspx)합니다.|  
|[CRowset](../../data/oledb/crowset-crowset.md)|새 `CRowset` (선택 사항)에 연결 하 고 개체는 **IRowset** 인터페이스 매개 변수로 제공 합니다.|  
|[삭제](../../data/oledb/crowset-delete.md)|사용 하 여 행 집합에서 행을 삭제 [IRowsetChange:DeleteRows](https://msdn.microsoft.com/en-us/library/ms724362.aspx)합니다.|  
|[FindNextRow](../../data/oledb/crowset-findnextrow.md)|지정된 된 책갈피 다음 다음 일치 하는 행을 찾습니다.|  
|[GetApproximatePosition](../../data/oledb/crowset-getapproximateposition.md)|해당 책갈피 하는 행의 대략적인 위치를 반환 합니다.|  
|[GetData](../../data/oledb/crowset-getdata.md)|행의 행 집합의 복사본에서 데이터를 검색합니다.|  
|[GetDataHere](../../data/oledb/crowset-getdatahere.md)|지정된 된 버퍼에서 데이터를 검색합니다.|  
|[GetOriginalData](../../data/oledb/crowset-getoriginaldata.md)|가장 최근에 풀에서 반입 되거나 보류 중인 변경 내용을 무시 하 고 데이터 원본에 전송 된 데이터를 검색 합니다.|  
|[GetRowStatus](../../data/oledb/crowset-getrowstatus.md)|모든 행의 상태를 반환 합니다.|  
|[삽입](../../data/oledb/crowset-insert.md)|만들고 사용 하 여 새 행을 삽입 [IRowsetChange:InsertRow](https://msdn.microsoft.com/en-us/library/ms716921.aspx)합니다.|  
|[IsSameRow](../../data/oledb/crowset-issamerow.md)|현재 행과 지정된 된 행을 비교합니다.|  
|[MoveFirst](../../data/oledb/crowset-movefirst.md)|다음 인출 위치를 처음 위치로 다시 설정합니다.|  
|[MoveLast](../../data/oledb/crowset-movelast.md)|마지막 레코드로 이동합니다.|  
|[MoveNext](../../data/oledb/crowset-movenext.md)|다음 순차적 행 이나 지정된 된 수의 다음 행을 초과 하는 위치에서 데이터를 인출합니다.|  
|[MovePrev](../../data/oledb/crowset-moveprev.md)|이전 레코드로 이동 합니다.|  
|[MoveToBookmark](../../data/oledb/crowset-movetobookmark.md)|이 책갈피에서 책갈피로 표시 행 이나 지정된 된 오프셋에 있는 행을 인출 합니다.|  
|[MoveToRatio](../../data/oledb/crowset-movetoratio.md)|행 집합의 소수 자릿수 위치에서 시작 하는 행을 인출 합니다.|  
|[ReleaseRows](../../data/oledb/crowset-releaserows.md)|호출 [irowset:: Releaserows](https://msdn.microsoft.com/en-us/library/ms719771.aspx) 현재 행 핸들을 해제 하도록 합니다.|  
|[SetData](../../data/oledb/crowset-setdata.md)|데이터 값을 사용 하 여 행의 하나 이상의 열에 설정 [IRowsetChange:SetData](https://msdn.microsoft.com/en-us/library/ms721232.aspx)합니다.|  
|[실행 취소](../../data/oledb/crowset-undo.md)|이후 마지막으로 인출 된 행에 대해 변경 내용을 실행 취소 또는 [업데이트](../../data/oledb/crowset-update.md)합니다.|  
|[업데이트](../../data/oledb/crowset-update.md)|보류 중인 마지막 페치 또는 업데이트 이후 현재 행에 대해 변경 내용을 전송 합니다.|  
|[UpdateAll](../../data/oledb/crowset-updateall.md)|보류 중인 마지막 페치 또는 업데이트 이후 모든 행에 대해 변경 내용을 전송 합니다.|  
  
## <a name="remarks"></a>설명  
 OLE DB 행 집합에는 있는 프로그램 설정 하 고 데이터 검색 개체입니다.  
  
 이 클래스는 인스턴스화할 수 있지만 대신를 템플릿 매개 변수로 전달으로 다루지는지 않습니다 `CTable` 또는 `CCommand` (`CRowset` 기본값임).  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [DBViewer 샘플](../../visual-cpp-samples.md)   
 [MultiRead 샘플](../../visual-cpp-samples.md)   
 [MultiRead 특성 샘플](../../visual-cpp-samples.md)   
 [OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB 소비자 템플릿 참조](../../data/oledb/ole-db-consumer-templates-reference.md)