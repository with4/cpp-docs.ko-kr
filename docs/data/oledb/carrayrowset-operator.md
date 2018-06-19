---
title: 'Carrayrowset:: Operator | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CArrayRowset::operator[]
- CArrayRowset.operator[]
dev_langs:
- C++
helpviewer_keywords:
- operator [], arrays
- '[] operator'
- operator[], arrays
ms.assetid: 3bb8c310-cc1e-46e8-9711-9b565488acaa
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 755e484f430f47eb072e3c590bfbee8471984bb6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33089129"
---
# <a name="carrayrowsetoperator"></a>CArrayRowset::operator
행 집합의 행 액세스에 대 한 배열 유사 구문을 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
      TAccessor  
      & operator[](int nrow);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `TAccessor`  
 행 집합에 저장 하는 접근자의 형식을 지정 하는 템플릿 매개 변수입니다.  
  
 `nRow`  
 [in] 액세스 하려는 행 (배열 요소)의 수입니다.  
  
## <a name="return-value"></a>반환 값  
 요청한 행의 내용입니다.  
  
## <a name="remarks"></a>설명  
 경우 `nRow` 행 집합의 행 수를 초과, 예외가 throw 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [CArrayRowset 클래스](../../data/oledb/carrayrowset-class.md)