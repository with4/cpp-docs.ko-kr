---
title: "스냅숏 | Microsoft Docs"
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
- ODBC cursor library [ODBC], snapshots
- cursors [ODBC], static
- recordsets, snapshots
- snapshots, support in ODBC
- static cursors
- ODBC recordsets, snapshots
- cursor library [ODBC], snapshots
- snapshots
ms.assetid: b5293a52-0657-43e9-bd71-fe3785b21c7e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: c31e08fdda3cef526f46946e45ef956f9ad1adaa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="snapshot"></a>스냅숏
스냅숏은은 스냅숏이 만들어진 때의 상태로 데이터의 정적 뷰를 반영 하는 레코드 집합입니다. 스냅숏 열고 모든 레코드를 이동 하면 포함 된 여러 레코드 집합 및 호출 하 여 스냅숏을 다시 만들 때까지 해당 값이 변경 되지 않는 **Requery**합니다.  
  
> [!NOTE]
>  MFC ODBC 클래스에이 항목에 적용 됩니다. MFC DAO 클래스와 MFC ODBC 클래스 대신 사용 하는 경우 참조 [cdaorecordset:: Open](../../mfc/reference/cdaorecordset-class.md#open) 에 대 한 설명은 스냅숏 형식 레코드 집합입니다.  
  
 데이터베이스 클래스와 업데이트 가능 하거나 읽기 전용 스냅숏을 만들 수 있습니다. 다이너셋, 달리 업데이트할 수 있는 스냅숏 레코드 값을 다른 사용자가 수행한 변경 내용을 반영 하지 않습니다 않지만 업데이트 및 삭제 사용자 프로그램에서 수행한 반영 합니다. 호출할 때까지 스냅숏으로에 추가 된 레코드는 스냅숏에 나타나지 지나지 않도록 **Requery**합니다.  
  
> [!TIP]
>  스냅숏은은 ODBC 정적 커서입니다. 해당 레코드를 스크롤할 때까지 정적 커서 데이터의 행을 실제로 발생 하지 않습니다. 모든 레코드를 즉시 검색을 보장 하려면 레코드 집합의 끝으로 스크롤하여 수 있으며 다음 보려는 첫 번째 레코드를 스크롤합니다. 그러나 끝으로 스크롤하면 과도 한 오버 헤드에 수반 되 고 성능을 저하 시킬 수 note 합니다.  
  
 스냅숏은 보고서를 작성 하거나 계산을 수행할 때 처럼 작업을 하는 동안 고정 된 상태로 유지할 데이터 유지 해야 하는 경우에 가장 중요 합니다. 데이터 원본 수를 분기 상당히 스냅샷을 않으므로 때때로 다시 작성 해야 할 수 있습니다.  
  
 스냅숏을 지원 위치 지정 업데이트 (업데이트 시 필요)에 대 한 모든 수준 1 드라이버 및 정적 커서를 제공 하는 ODBC 커서 라이브러리를 기반으로 합니다. 커서 라이브러리 DLL이이 지원에 대 한 메모리에 로드 해야 합니다. 생성할 때는 `CDatabase` 개체와 호출 해당 `OpenEx` 지정 해야 멤버 함수는 **CDatabase::useCursorLib** 옵션의는 `dwOptions` 매개 변수입니다. 호출 하는 경우는 **열려** 멤버 함수를 커서 라이브러리는 기본적으로 로드 됩니다. 다이너셋 스냅샷 대신를 사용 하는 경우 커서 라이브러리를 로드 하지 않을 수 있습니다.  
  
 ODBC 커서 라이브러리 때 로드 된 경우에 사용할 수 있는 스냅숏이 `CDatabase` 생성 된 개체 또는 ODBC 드라이버를 사용 하는 정적 커서를 지원 합니다.  
  
> [!NOTE]
>  일부 ODBC 드라이버 스냅샷 (정적 커서)을 업데이트 하지 못할 수도 있습니다. 지원 되는 커서 형식에 대 한 드라이버 설명서를 지 원하는 동시성 유형은 확인 합니다. 스냅숏을 업데이트할 수 있으려면를 만들 때 메모리에 커서 라이브러리를 로드 있는지 확인 한 `CDatabase` 개체입니다. 자세한 내용은 참조 [ODBC: ODBC 커서 라이브러리](../../data/odbc/odbc-the-odbc-cursor-library.md)합니다.  
  
> [!NOTE]
>  스냅숏과 다이너셋 사용 하려는 경우 두 개의 다른에 기반 해야 `CDatabase` 개체 (두 개의 서로 다른 연결).  
  
 모든 레코드 집합과 속성 스냅숏 공유에 대 한 자세한 내용은 참조 [레코드 집합 (ODBC)](../../data/odbc/recordset-odbc.md)합니다. ODBC 및 스냅숏, ODBC 커서 라이브러리를 포함 하는 방법에 대 한 자세한 내용은 참조 [ODBC](../../data/odbc/odbc-basics.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [ODBC(Open Database Connectivity)](../../data/odbc/open-database-connectivity-odbc.md)