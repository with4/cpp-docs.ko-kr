---
title: '레코드 집합: 대량 (ODBC) 레코드 추가 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ODBC recordsets, adding records
- recordsets, adding records
- bulk record additions to recordsets
ms.assetid: 4685f656-14b9-4f10-a1c5-147b2b89a0b4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7bb39b910eae797f360513954ad0c32d5e99bb86
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="recordset-adding-records-in-bulk-odbc"></a>레코드 집합: 대량 레코드 추가(ODBC)
MFC ODBC 클래스에이 항목에 적용 됩니다.  
  
 MFC [CRecordset](../../mfc/reference/crecordset-class.md) 클래스에 최적화 테이블에 새 레코드를 일괄 추가할 때 효율성을 향상 합니다.  
  
> [!NOTE]
>  이 항목에서 파생 된 개체에 적용 됩니다. `CRecordset` 에서 대량 행 페치 구현 되지 않았습니다. 대량 행 페치를 사용 하는 경우 참조 [레코드 집합: 레코드 페치 대량 (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)합니다.  
  
 에 대 한 새 옵션은 **dwOptions** 매개 변수를는 [crecordset:: Open](../../mfc/reference/crecordset-class.md#open) 멤버 함수 **optimizeBulkAdd**을 하면 여러 레코드를 추가 하는 경우 성능이 향상 호출 하지 않고 연속적으로 **Requery** 또는 **닫기**합니다. 첫 번째 변경 되는 필드에만 **업데이트** 호출 다음에 대 한 커밋되지 않은 것으로 표시 된 `AddNew` / **업데이트** 호출 합니다.  
  
 활용 하기 위해 데이터베이스 클래스를 사용 하는 경우는 **:: SQLSetPos** 편집, ODBC API 함수를 추가 하 고 레코드를 삭제,이 최적화 필요 하지 않습니다.  
  
 ODBC 커서 라이브러리가 로드 하거나 ODBC 드라이버는 추가 지원 하지 않습니다, 편집 및 통해 삭제 **:: SQLSetPos**,이 최적화 대량 개선 해야 성능 추가 합니다. 이 최적화를 활성화 하려면 설정는 **dwOptions** 에서 매개 변수는 **열려** 다음과 레코드 집합에 대 한 호출:  
  
```  
appendOnly | optimizeBulkAdd  
```  
  
## <a name="see-also"></a>참고 항목  
 [레코드 집합 (ODBC)](../../data/odbc/recordset-odbc.md)   
 [레코드 집합: 추가, 업데이트 및 삭제할 레코드 (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)   
 [레코드 집합: 레코드 잠금(ODBC)](../../data/odbc/recordset-locking-records-odbc.md)