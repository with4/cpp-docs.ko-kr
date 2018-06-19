---
title: 'Crowset:: Findnextrow | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.CRowset.FindNextRow
- CRowset<TAccessor>.FindNextRow
- ATL::CRowset::FindNextRow
- CRowset::FindNextRow
- CRowset<TAccessor>::FindNextRow
- CRowset.FindNextRow
- ATL.CRowset<TAccessor>.FindNextRow
- ATL::CRowset<TAccessor>::FindNextRow
- FindNextRow
dev_langs:
- C++
helpviewer_keywords:
- FindNextRow method
ms.assetid: 36484df9-3625-4f15-bf69-db73a8d91c55
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 4afc1db20970102ecddb9031f4f1b7a8f6906cf4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33098226"
---
# <a name="crowsetfindnextrow"></a>CRowset::FindNextRow
지정된 된 책갈피 다음 다음 일치 하는 행을 찾습니다.  
  
## <a name="syntax"></a>구문  
  
```
HRESULT FindNextRow(DBCOMPAREOP op,   
  BYTE* pData,   
   DBTYPE wType,   
   DBLENGTH nLength,   
   BYTE bPrecision,   
   BYTE bScale,   
   BOOL bSkipCurrent = TRUE,   
   CBookmarkBase* pBookmark = NULL) throw();  
```  
  
#### <a name="parameters"></a>매개 변수  
 `op`  
 [in] 행 값을 비교할 때 사용 하는 작업입니다. 값을 참조 하십시오. [irowsetfind:: Findnextrow](https://msdn.microsoft.com/en-us/library/ms723091.aspx)합니다.  
  
 `pData`  
 [in] 일치 시킬 값에 대 한 포인터입니다.  
  
 `wType`  
 [in] 버퍼의 값 부분의 데이터 형식을 나타냅니다. 형식 표시기에 대 한 정보를 참조 하십시오. [데이터 형식](https://msdn.microsoft.com/en-us/library/ms723969.aspx) 에 *OLE DB 프로그래머 참조* Windows sdk에서입니다.  
  
 `nLength`  
 [in] 데이터 값에 할당 된 소비자 데이터 구조의 길이 (바이트)를 합니다. 자세한 내용은 설명을 참조 **cbMaxLen** 에 [DBBINDING 구조](https://msdn.microsoft.com/en-us/library/ms716845.aspx) 에 *OLE DB 프로그래머 참조 합니다.*  
  
 `bPrecision`  
 [in] 데이터를 가져올 때 사용 되는 최대 전체 자릿수입니다. 사용 되는 경우에만 `wType` 은 `DBTYPE_NUMERIC`합니다. 자세한 내용은 참조 [DBTYPE_NUMERIC 또는 DBTYPE_DECIMAL와 관련 된 변환](https://msdn.microsoft.com/en-us/library/ms719714.aspx) 에 *OLE DB Programmer's Reference*합니다.  
  
 `bScale`  
 [in] 데이터를 가져올 때 사용 되는 배율입니다. 사용 되는 경우에만 `wType` 은 `DBTYPE_NUMERIC` 또는 **DBTYPE_DECIMAL**합니다. 자세한 내용은 참조 [DBTYPE_NUMERIC 또는 DBTYPE_DECIMAL와 관련 된 변환](https://msdn.microsoft.com/en-us/library/ms719714.aspx) 에 *OLE DB Programmer's Reference*합니다.  
  
 *bSkipCurrent*  
 [in] 검색을 시작 하는 책갈피에서의 행 수입니다.  
  
 `pBookmark`  
 [in] 검색을 시작 하는 위치에 대 한 책갈피입니다.  
  
## <a name="return-value"></a>반환 값  
 표준 `HRESULT`입니다.  
  
## <a name="remarks"></a>설명  
 이 메서드를 사용 하려면 선택적 인터페이스 **IRowsetFind**, 모든 공급자에서 지원 되지 않는 있는;의 경우이 메서드는 반환 **E_NOINTERFACE**합니다. 설정 해야 **DBPROP_IRowsetFind** 를 `VARIANT_TRUE` 호출 하기 전에 **열려** 테이블이 나 행 집합을 포함 하는 명령입니다.  
  
 소비자에 책갈피를 사용 하는 방법에 대 한 정보를 참조 하십시오. [책갈피를 사용 하 여](../../data/oledb/using-bookmarks.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [CRowset 클래스](../../data/oledb/crowset-class.md)   
 [DBBINDING 구조](https://msdn.microsoft.com/en-us/library/ms716845.aspx)