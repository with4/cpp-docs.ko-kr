---
title: CRowset::GetApproximatePosition | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CRowset::GetApproximatePosition
- ATL::CRowset<TAccessor>::GetApproximatePosition
- CRowset.GetApproximatePosition
- CRowset::GetApproximatePosition
- GetApproximatePosition
- ATL.CRowset.GetApproximatePosition
- CRowset<TAccessor>::GetApproximatePosition
dev_langs:
- C++
helpviewer_keywords:
- GetApproximatePosition method
ms.assetid: 8f9ccd41-0590-468e-b202-6731d0f99d21
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ae92a7734c3b6f763ab4d6731e1cb8ff5222c676
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="crowsetgetapproximateposition"></a>CRowset::GetApproximatePosition
해당 책갈피 하는 행의 대략적인 위치를 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT GetApproximatePosition(const CBookmarkBase* pBookmark,   
   DBCOUNTITEM* pPosition,   
   DBCOUNTITEM* pcRows) throw();  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pBookmark`  
 [in] 위치가 있어야 하는 행을 식별 하는 책갈피에 대 한 포인터입니다. **NULL** 만 행 수는 필수입니다.  
  
 *pPosition*  
 [out] 위치에 대 한 포인터를 `GetApproximatePosition` 행의 위치를 반환 합니다. **NULL** 위치 필요 하지 않은 경우.  
  
 `pcRows`  
 [out] 위치에 대 한 포인터를 `GetApproximatePosition` 행의 총 수를 반환 합니다. **NULL** 행 개수 필요 하지 않은 경우.  
  
## <a name="return-value"></a>반환 값  
 표준 `HRESULT`입니다.  
  
## <a name="remarks"></a>설명  
 이 메서드를 사용 하려면 선택적 인터페이스 `IRowsetScroll`, 모든 공급자에서 지원 되지 않는 있는;의 경우이 메서드는 반환 **E_NOINTERFACE**합니다. 설정 해야 **DBPROP_IRowsetScroll** 를 `VARIANT_TRUE` 호출 하기 전에 **열려** 테이블이 나 행 집합을 포함 하는 명령입니다.  
  
 소비자에 책갈피를 사용 하는 방법에 대 한 정보를 참조 하십시오. [책갈피를 사용 하 여](../../data/oledb/using-bookmarks.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [CRowset 클래스](../../data/oledb/crowset-class.md)   
 [IRowsetScroll::GetApproximatePosition](https://msdn.microsoft.com/en-us/library/ms712901.aspx)