---
title: 'Crowset:: Movenext | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.CRowset<TAccessor>.MoveNext
- ATL.CRowset.MoveNext
- ATL::CRowset<TAccessor>::MoveNext
- CRowset<TAccessor>.MoveNext
- CRowset.MoveNext
- CRowset<TAccessor>::MoveNext
- CRowset::MoveNext
- ATL::CRowset::MoveNext
dev_langs: C++
helpviewer_keywords: MoveNext method
ms.assetid: 0df3288c-2bce-494f-99c0-6344b54a4adf
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e2b0a3a3a10ae2cc18ab83800cc50f25903a3607
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="crowsetmovenext"></a>CRowset::MoveNext
커서를 다음 레코드로 이동합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      HRESULT MoveNext( ) throw( );   
HRESULT MoveNext(   
   LONG lSkip,   
   bool bForward = true    
) throw( );  
```  
  
#### <a name="parameters"></a>매개 변수  
 `lSkip`  
 [in] 인출 하기 전에 건너뛸 행 수입니다.  
  
 `bForward`  
 [in] 전달 **true** 를 다음 레코드로 앞으로 이동 하려면 **false** 뒤로 이동 하려면.  
  
## <a name="return-value"></a>반환 값  
 표준 `HRESULT`입니다. 행 집합의 끝에 도달한 경우 반환 **DB_S_ENDOFROWSET**합니다.  
  
## <a name="remarks"></a>설명  
 다음 순차적인 행 인출는 `CRowset` 개체를 이전 위치를 기억 합니다. 선택적으로 바로 이동 하도록 선택할 수 있습니다 `lSkip` 행 또는 뒤로 이동 합니다.  
  
 이 메서드 호출 하기 전에 다음과 같은 속성을 설정 해야 **열려** 테이블이 나 행 집합에 포함 된 명령:  
  
-   **DBPROP_CANSCROLLBACKWARDS** 해야 `VARIANT_TRUE` 경우 `lSkip` < 0  
  
-   **DBPROP_CANFETCHBACKWARDS** 해야 `VARIANT_TRUE` 경우 `bForward` = false  
  
 그렇지 않은 경우 (경우 `lSkip` > = 0 및 `bForward` = true)를 추가 속성을 설정할 필요가 없습니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [CRowset 클래스](../../data/oledb/crowset-class.md)   
 [Crowset:: Movefirst](../../data/oledb/crowset-movefirst.md)   
 [Crowset:: Movetobookmark](../../data/oledb/crowset-movetobookmark.md)   
 [Crowset:: Moveprev](../../data/oledb/crowset-moveprev.md)   
 [CRowset::MoveLast](../../data/oledb/crowset-movelast.md)