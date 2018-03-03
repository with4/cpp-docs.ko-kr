---
title: "레코드 집합: 집합 만들기 및 닫기 (ODBC) 레코드 집합 | Microsoft Docs"
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
- ODBC recordsets, creating
- recordsets, creating
- recordsets, opening
- recordsets, closing
- ODBC recordsets, closing
- ODBC recordsets, opening
ms.assetid: 8d2aac23-4396-4ce2-8c60-5ecf1b360d3d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 9ec09c08aa4730c11960d675aef68c8a1007c900
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="recordset-creating-and-closing-recordsets-odbc"></a>레코드 집합: 레코드 집합 만들기 및 닫기(ODBC)
MFC ODBC 클래스에이 항목에 적용 됩니다.  
  
 레코드 집합을 사용 하려면 레코드 집합 개체를 생성 한 다음 호출 해당 **열려** 멤버 함수를 레코드 집합의 쿼리를 실행 하 고 레코드를 선택 합니다. 레코드 집합을 마치면 닫고 개체를 삭제 합니다.  
  
 이 항목에 설명 합니다.  
  
-   [Recordset 개체를 만드는 방법과 시기](#_core_creating_recordsets_at_run_time)합니다.  
  
-   [매개 변수화, 필터링, 정렬, 또는 잠금을 레코드 집합의 동작을 한정할 수 있습니다 시기와 방법을](#_core_setting_recordset_options)합니다.  
  
-   [레코드 집합 개체를 닫는 방법과 시기](#_core_closing_a_recordset)합니다.  
  
##  <a name="_core_creating_recordsets_at_run_time"></a>런타임 시 레코드 집합 만들기  
 프로그램에서 레코드 집합 개체를 만들 수 있습니다, 전에 일반적으로 응용 프로그램 관련 레코드 집합 클래스를 작성 합니다. 이 예비 단계에 대 한 자세한 내용은 참조 [MFC ODBC 소비자 추가](../../mfc/reference/adding-an-mfc-odbc-consumer.md)합니다.  
  
 데이터 원본에서 레코드를 선택 해야 스냅숏 엽니다. 만들 개체의 형식은 필요한 항목에 따라 다릅니다. 지 원하는 ODBC 드라이버와 응용 프로그램에 데이터를 사용 합니다. 자세한 내용은 참조 [다이너셋](../../data/odbc/dynaset.md) 및 [스냅숏](../../data/odbc/snapshot.md)합니다.  
  
#### <a name="to-open-a-recordset"></a>레코드 집합을 열려면  
  
1.  개체를 생성 하면 `CRecordset`-클래스를 파생 합니다.  
  
     함수의 스택 프레임 또는 힙의 개체를 생성할 수 있습니다.  
  
2.  필요에 따라 기본 레코드 집합 동작을 수정 합니다. 사용 가능한 옵션에 대 한 참조 [레코드 집합 옵션 설정](#_core_setting_recordset_options)합니다.  
  
3.  개체의 [열려](../../mfc/reference/crecordset-class.md#open) 멤버 함수입니다.  
  
 생성자에 전달에 대 한 포인터는 `CDatabase` 개체 **NULL** 반환 하는 연결 문자열에 따라 데이터베이스 개체는 프레임 워크를 생성 하 고 엽니다 임시를 사용 하 여 [GetDefaultConnect ](../../mfc/reference/crecordset-class.md#getdefaultconnect) 멤버 함수입니다. `CDatabase` 개체 데이터 소스에 이미 연결 되어 있습니다.  
  
 에 대 한 호출 **열려** SQL을 사용 하 여 데이터 원본에서 레코드를 선택 합니다. (있는 경우)를 선택 하는 첫 번째 레코드는 현재 레코드입니다. 이 레코드의이 필드의 값은 레코드 집합 개체의 필드 데이터 멤버에 저장 됩니다. 레코드 선택 된 경우 둘 다는 `IsBOF` 및 `IsEOF` 멤버 함수는 0을 반환 합니다.  
  
 사용자 [열려](../../mfc/reference/crecordset-class.md#open) 호출을 수행할 수 있습니다.  
  
-   다이너셋 또는 스냅숏을 레코드 집합 인지 여부를 지정 합니다. 기본적으로 스냅숏으로 레코드 집합을 엽니다. 또는 앞 으로만 이동 가능한 레코드 집합 앞 으로만 스크롤, 한 번에 하나의 레코드 수를 지정할 수 있습니다.  
  
     레코드 집합을 기본적으로에 저장 된 기본 형식 사용은 `CRecordset` 데이터 멤버 **m_nDefaultType**합니다. 마법사가 초기화 하는 코드 작성 **m_nDefaultType** 는 마법사에서 선택한 레코드 집합 형식에 있습니다. 이 기본값을 적용 하는 대신 다른 레코드 집합 형식을 대체할 수 있습니다.  
  
-   기본 SQL를 대체 하는 문자열을 지정 **선택** 레코드 집합에서 생성 하는 문입니다.  
  
-   읽기 전용 또는 추가 전용 레코드 집합 인지 여부를 지정 합니다. 레코드 집합 전체 기본적으로 업데이트가 허용 되지만 추가 새 레코드로 제한 또는 모든 업데이트를 거부할 수 있습니다.  
  
 다음 예제에서는 클래스의 읽기 전용 스냅숏 개체 `CStudentSet`, 응용 프로그램별 클래스:  
  
```  
// Construct the snapshot object  
CStudentSet rsStudent( NULL );  
// Set options if desired, then open the recordset  
if(!rsStudent.Open(CRecordset::snapshot, NULL, CRecordset::readOnly))  
    return FALSE;  
// Use the snapshot to operate on its records...  
```  
  
 호출한 후 **열려**, 레코드를 사용 하려면 개체의 멤버 함수 및 데이터 멤버를 사용 합니다. 경우에 따라 쿼리하거나 데이터 소스에서 발생 한 변경 내용을 포함 하도록 레코드 집합을 새로 고치지는 것이 좋습니다. 자세한 내용은 참조 [레코드 집합: 레코드 집합 (ODBC) 다시 쿼리](../../data/odbc/recordset-requerying-a-recordset-odbc.md)합니다.  
  
> [!TIP]
>  개발 중에 사용 되는 연결 문자열 최종 사용자에 게 필요한 동일한 연결 문자열을 수 있습니다. 이런 점에서 응용 프로그램을 일반화 하는 방법에 대 한 아이디어를 참조 하십시오. [데이터 소스: 연결 관리 (ODBC)](../../data/odbc/data-source-managing-connections-odbc.md)합니다.  
  
##  <a name="_core_setting_recordset_options"></a>레코드 집합 옵션 설정  
 레코드 집합 개체를 생성 한 후 있지만 호출 하기 전에 **열려** 레코드를 선택 하려면 레코드 집합의 동작을 제어 하는 몇 가지 옵션을 설정 수 있습니다. 모든 레코드 집합에 대 한 다음 작업을 수행할 수 있습니다.  
  
-   지정 된 [필터](../../data/odbc/recordset-filtering-records-odbc.md) 레코드 선택을 제한 하 합니다.  
  
-   지정 된 [정렬](../../data/odbc/recordset-sorting-records-odbc.md) 레코드 순서입니다.  
  
-   지정 [매개 변수](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md) 가져오거나 런타임 시 계산 된 정보를 사용 하 여 레코드를 선택할 수 있도록 합니다.  
  
 조건을 만족 하는 경우에 다음과 같은 옵션을 설정할 수 있습니다.  
  
-   레코드 집합을 업데이트할 수이 고 잠금 옵션을 지원 하는 경우 지정 된 [잠금](../../data/odbc/recordset-locking-records-odbc.md) 업데이트를 사용 하는 방법입니다.  
  
> [!NOTE]
>  레코드 선택에 영향을 주지만 하려면 설정 해야를 호출 하기 전에 이러한 옵션은 **열려** 멤버 함수입니다.  
  
##  <a name="_core_closing_a_recordset"></a>레코드 집합을 닫으면  
 레코드 집합을 마치면 삭제 하 고 메모리 할당을 취소 해야 합니다.  
  
#### <a name="to-close-a-recordset"></a>레코드 집합을 닫으려면  
  
1.  호출의 [닫기](../../mfc/reference/crecordset-class.md#close) 멤버 함수입니다.  
  
2.  레코드 집합 개체를 제거 합니다.  
  
     함수의 스택 프레임에 선언한 경우 개체는 범위를 벗어날 때 자동으로 소멸 됩니다. 그렇지 않은 경우 사용 된 **삭제** 연산자입니다.  
  
 **닫기** 레코드 집합의 실행을 해제 **HSTMT** 처리 합니다. C + + 개체는 삭제 되지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [레코드 집합 (ODBC)](../../data/odbc/recordset-odbc.md)   
 [레코드 집합: 스크롤 (ODBC)](../../data/odbc/recordset-scrolling-odbc.md)   
 [레코드 집합: 레코드 추가, 업데이트 및 삭제(ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)