---
title: 'Cbulkrowset:: Movetoratio | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CBulkRowset.MoveToRatio
- ATL::CBulkRowset::MoveToRatio
- MoveToRatio
- CBulkRowset::MoveToRatio
- ATL.CBulkRowset<TAccessor>.MoveToRatio
- ATL::CBulkRowset<TAccessor>::MoveToRatio
- ATL.CBulkRowset.MoveToRatio
- CBulkRowset<TAccessor>::MoveToRatio
dev_langs:
- C++
helpviewer_keywords:
- MoveToRatio method
ms.assetid: 86be60f5-9341-44c1-8e1e-9174c082d0d5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 0ab702781ed47a4520b53e9698319b5c245e2dfc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33093362"
---
# <a name="cbulkrowsetmovetoratio"></a>CBulkRowset::MoveToRatio
행 집합의 소수 자릿수 위치에서 시작 하는 행을 인출 합니다.  
  
## <a name="syntax"></a>구문  
  
```
HRESULT MoveToRatio(DBCOUNTITEM nNumerator,  
   DBCOUNTITEM nDenominator)throw();  
```  
  
#### <a name="parameters"></a>매개 변수  
 `nNumerator`  
 [in] 분자 데이터를 가져올 수 있는 소수 자릿수 위치를 결정 하는 데 사용 합니다.  
  
 `nDenominator`  
 [in] 분모의 데이터를 가져올 수 있는 소수 자릿수 위치를 결정 하는 데 사용 합니다.  
  
## <a name="return-value"></a>반환 값  
 표준 `HRESULT`입니다.  
  
## <a name="remarks"></a>설명  
 `MoveToRatio` 다음 식에 따라 약 행을 인출 합니다.  
  
 `(nNumerator *  RowsetSize ) / nDenominator`  
  
 여기서 `RowsetSize` (행) 행 집합의 크기입니다. 이 수식은의 정확도 특정 공급자에 따라 달라 집니다. 자세한 내용은 참조 [irowsetscroll::](https://msdn.microsoft.com/en-us/library/ms709602.aspx) 에 *OLE DB Programmer's Reference*합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [CBulkRowset 클래스](../../data/oledb/cbulkrowset-class.md)