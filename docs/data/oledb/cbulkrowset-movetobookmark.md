---
title: 'Cbulkrowset:: Movetobookmark | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CBulkRowset<TAccessor>::MoveToBookmark
- CBulkRowset.MoveToBookmark
- MoveToBookmark
- ATL.CBulkRowset.MoveToBookmark
- CBulkRowset::MoveToBookmark
- ATL::CBulkRowset<TAccessor>::MoveToBookmark
- ATL::CBulkRowset::MoveToBookmark
dev_langs:
- C++
helpviewer_keywords:
- MoveToBookmark method
ms.assetid: 76aab025-819e-4ecd-ae0a-d8d3fb2d2099
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 4b1911fe170262e65ef06e65649f837a0b723d05
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="cbulkrowsetmovetobookmark"></a>CBulkRowset::MoveToBookmark
책갈피 또는 지정된 된 오프셋에 있는 행으로 표시 된 행 인출 (`lSkip`) 해당 책갈피에서 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT MoveToBookmark(const CBookmarkBase& bookmark,  
   DBCOUNTITEM lSkip = 0) throw();  
```  
  
#### <a name="parameters"></a>매개 변수  
 `bookmark`  
 [in] 데이터를 인출 하려는 위치를 표시 하는 책갈피입니다.  
  
 `lSkip`  
 [in] 대상 행에 책갈피에서 행의 번호 수입니다. 경우 `lSkip` 가 0 인 경우 인출 된 첫 번째 행은 책갈피가 표시 된 행입니다. 경우 `lSkip` 이 1 이면 후 책갈피가 표시 된 행은 행을 인출 된 첫 번째 행입니다. 경우 `lSkip` -1 이면 첫 번째 인출 된 행은 책갈피가 표시 된 행 앞에 있는 행입니다.  
  
## <a name="return-value"></a>반환 값  
 참조 [irowset:: Getdata](https://msdn.microsoft.com/en-us/library/ms716988.aspx) 에 *OLE DB Programmer's Reference*합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [CBulkRowset 클래스](../../data/oledb/cbulkrowset-class.md)