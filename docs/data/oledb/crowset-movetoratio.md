---
title: 'Crowset:: Movetoratio | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- MoveToRatio
- CRowset<TAccessor>::MoveToRatio
- CRowset::MoveToRatio
- CRowset<TAccessor>.MoveToRatio
- ATL.CRowset.MoveToRatio
- ATL::CRowset::MoveToRatio
- CRowset.MoveToRatio
- ATL.CRowset<TAccessor>.MoveToRatio
- ATL::CRowset<TAccessor>::MoveToRatio
dev_langs:
- C++
helpviewer_keywords:
- MoveToRatio method
ms.assetid: 1fa313bd-8fd1-4608-8e85-44993b97dd88
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 9c864933070af4f2a40572d0133027fb81f0855a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="crowsetmovetoratio"></a>CRowset::MoveToRatio
행 집합의 소수 자릿수 위치에서 시작 하는 행을 인출 합니다.  
  
## <a name="syntax"></a>구문  
  
```
HRESULT MoveToRatio(DBCOUNTITEM nNumerator,   
   DBCOUNTITEM nDenominator,bool bForward = true) throw();  
```  
  
#### <a name="parameters"></a>매개 변수  
 `nNumerator`  
 [in] 소수 자릿수를 결정 하는 데 사용 되는 분자 데이터를 가져올 수 있는 위치입니다.  
  
 `nDenominator`  
 [in] 분모는 소수 자릿수를 확인 하는 데 데이터를 가져올 수 있는 위치입니다.  
  
 `bForward`  
 [in] 앞으로 또는 뒤로 이동 여부를 나타냅니다. 기본값은 앞으로.  
  
## <a name="return-value"></a>반환 값  
 표준 `HRESULT`입니다.  
  
## <a name="remarks"></a>설명  
 `MoveToRatio` 다음 수식에 대략에 따라 행을 인출 합니다.  
  
 `(nNumerator *  RowsetSize ) / nDenominator`  
  
 여기서 `RowsetSize` (행) 행 집합의 크기입니다. 이 수식은의 정확도 특정 공급자에 따라 달라 집니다. 자세한 내용은 참조 [irowsetscroll::](https://msdn.microsoft.com/en-us/library/ms709602.aspx)합니다.  
  
 이 메서드를 사용 하려면 선택적 인터페이스 `IRowsetScroll`, 모든 공급자에서 지원 되지 않는 있는;의 경우이 메서드는 반환 **E_NOINTERFACE**합니다. 설정 해야 **DBPROP_IRowsetScroll** 를 `VARIANT_TRUE` 호출 하기 전에 **열려** 테이블이 나 행 집합을 포함 하는 명령입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [CRowset 클래스](../../data/oledb/crowset-class.md)