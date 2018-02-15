---
title: CRowset::MoveToBookmark | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::CRowset::MoveToBookmark
- ATL::CRowset<TAccessor>::MoveToBookmark
- ATL.CRowset.MoveToBookmark
- ATL.CRowset<TAccessor>.MoveToBookmark
- MoveToBookmark
- CRowset::MoveToBookmark
- CRowset.MoveToBookmark
- CRowset<TAccessor>::MoveToBookmark
dev_langs:
- C++
helpviewer_keywords:
- MoveToBookmark method
ms.assetid: 90124723-8daf-4692-ae2f-0db26b5db920
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2e443cace051fc0d5c08381222f0cd6aa53bec8f
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="crowsetmovetobookmark"></a>CRowset::MoveToBookmark
책갈피 또는 지정된 된 오프셋에 있는 행으로 표시 된 행 인출 (`lSkip`) 해당 책갈피에서 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT MoveToBookmark(const CBookmarkBase& bookmark,   
   LONG lSkip = 0) throw();  
```  
  
#### <a name="parameters"></a>매개 변수  
 `bookmark`  
 [in] 데이터를 인출 하려는 위치를 표시 하는 책갈피입니다.  
  
 `lSkip`  
 [in] 대상 행에 책갈피에서 행의 번호 수입니다. 경우 `lSkip` 가 0 인 경우 인출 된 첫 번째 행은 책갈피가 표시 된 행입니다. 경우 `lSkip` 이 1 이면 후 책갈피가 표시 된 행은 행을 인출 된 첫 번째 행입니다. 경우 `lSkip` -1 이면 첫 번째 인출 된 행은 책갈피가 표시 된 행 앞에 있는 행입니다.  
  
## <a name="return-value"></a>반환 값  
 표준 `HRESULT`입니다.  
  
## <a name="remarks"></a>설명  
 이 메서드를 사용 하려면 선택적 인터페이스 `IRowsetLocate`, 모든 공급자에서 지원 되지 않는 있는;의 경우이 메서드는 반환 **E_NOINTERFACE**합니다. 설정 해야 **DBPROP_IRowsetLocate** 를 `VARIANT_TRUE` 설정 **DBPROP_CANFETCHBACKWARDS** 를 `VARIANT_TRUE` 호출 하기 전에 **열려** 테이블이 나 명령에서 행 집합을 포함 합니다.  
  
 소비자에 책갈피를 사용 하는 방법에 대 한 정보를 참조 하십시오. [책갈피를 사용 하 여](../../data/oledb/using-bookmarks.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [CRowset 클래스](../../data/oledb/crowset-class.md)   
 [CRowset::MoveNext](../../data/oledb/crowset-movenext.md)   
 [CRowset::MoveFirst](../../data/oledb/crowset-movefirst.md)   
 [IRowsetLocate::GetRowsAt](https://msdn.microsoft.com/en-us/library/ms723031.aspx)   
 [CRowset::MovePrev](../../data/oledb/crowset-moveprev.md)   
 [CRowset::MoveLast](../../data/oledb/crowset-movelast.md)