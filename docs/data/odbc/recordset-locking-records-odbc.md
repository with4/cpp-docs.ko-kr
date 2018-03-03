---
title: "레코드 집합: 레코드 잠금 (ODBC) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- locks [C++], recordsets
- optimistic locking
- pessimistic locking in ODBC
- recordsets [C++], locking records
- optimistic locking, ODBC
- ODBC recordsets [C++], locking records
- data [C++], locking
ms.assetid: 8fe8fcfe-b55a-41a8-9136-94a7cd1e4806
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 76d7ab2df01e485ffff70120609227b9fbae6ac5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="recordset-locking-records-odbc"></a>레코드 집합: 레코드 잠금(ODBC)
MFC ODBC 클래스에이 항목에 적용 됩니다.  
  
 이 항목에 설명 합니다.  
  
-   [사용 가능한 레코드 잠금 종류](#_core_record.2d.locking_modes)합니다.  
  
-   [업데이트 중 레코드 집합의 레코드를 잠그는 방법](#_core_locking_records_in_your_recordset)합니다.  
  
 레코드 집합을 사용 하 여 데이터 원본에서 레코드를 업데이트 하는 경우 동시에 다른 사용자 레코드를 업데이트할 수 있도록 응용 프로그램는 레코드를 잠글 수 있습니다. 시스템에서 두 사용자가 레코드를 동시에 업데이트할 수를 보장할 수 없는 두 사용자가 동시에 업데이트 하는 레코드의 상태가 정의 되지 않습니다.  
  
> [!NOTE]
>  이 항목에서 파생 된 개체에 적용 됩니다. `CRecordset` 에서 대량 행 페치 구현 되지 않았습니다. 대량 행 페치를 구현한 경우이 정보 중 일부는 적용 되지 않습니다. 예를 들어, 호출할 수 없습니다는 **편집** 및 **업데이트** 멤버 함수입니다. 대량 행 페치에 대 한 자세한 내용은 참조 [레코드 집합: 레코드 페치 대량 (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)합니다.  
  
##  <a name="_core_record.2d.locking_modes"></a>레코드 잠금 모드  
 데이터베이스 클래스에서 제공 두 [레코드 잠금 모드](../../mfc/reference/crecordset-class.md#setlockingmode):  
  
-   낙관적 잠금 (기본값)  
  
-   비관적 잠금  
  
 3 단계에 따라 발생 한 레코드를 업데이트 합니다.  
  
1.  작업을 호출 하 여 시작 된 [편집](../../mfc/reference/crecordset-class.md#edit) 멤버 함수입니다.  
  
2.  현재 레코드의 해당 필드를 변경 합니다.  
  
3.  작업-정상적으로 업데이트를 커밋합니다-호출 하 여는 [업데이트](../../mfc/reference/crecordset-class.md#update) 멤버 함수입니다.  
  
 중에 데이터 원본에서 레코드를 잠급니다 낙관적 잠금는 **업데이트** 호출 합니다. 낙관적 잠금 다중 사용자 환경에서 사용 하는 경우 응용 프로그램 처리 하는 **업데이트** 오류 상태입니다. 호출 되는 즉시 레코드를 잠그는 비관적 잠금 **편집** 해제 하지 않는다는 것 할 때까지 호출 **업데이트** (오류를 통해 표시 됩니다는 `CDBException` 값이아니라메커니즘**FALSE** 반환한 **업데이트**). 비관적 잠금에서는 다른 사용자에 대해서는 성능이 저하 같은 레코드에 대 한 동시 액세스를 응용 프로그램의 완료 될 때까지 기다려야 할 수 있으므로 **업데이트** 프로세스입니다.  
  
##  <a name="_core_locking_records_in_your_recordset"></a>레코드 집합의 레코드 잠금  
 레코드 집합 개체의 변경 하려는 경우 [잠금 모드](#_core_record.2d.locking_modes) 기본값에서 변경 해야를 호출 하기 전에 모드 **편집**합니다.  
  
#### <a name="to-change-the-current-locking-mode-for-your-recordset"></a>레코드 집합에 대 한 현재 잠금 모드를 변경 하려면  
  
1.  호출 된 [SetLockingMode](../../mfc/reference/crecordset-class.md#setlockingmode) 멤버 함수를 지정 하 **CRecordset::pessimistic** 또는 **CRecordset::optimistic**합니다.  
  
 새 잠금 모드는 다시 변경 하거나 레코드 집합 닫힐 때까지 적용 됩니다.  
  
> [!NOTE]
>  ODBC 드라이버는 많지 비관적 잠금을 현재 지원 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [레코드 집합 (ODBC)](../../data/odbc/recordset-odbc.md)   
 [레코드 집합: 조인 수행 (ODBC)](../../data/odbc/recordset-performing-a-join-odbc.md)   
 [레코드 집합: 레코드 추가, 업데이트 및 삭제(ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)