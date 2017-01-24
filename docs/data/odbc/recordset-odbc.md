---
title: "레코드 집합(ODBC) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "동적 레코드 집합"
  - "다이너셋"
  - "앞으로만 이동 가능한 레코드 집합"
  - "ODBC 레코드 집합"
  - "ODBC 레코드 집합, CRecordset 개체"
  - "레코드 집합, 레코드 집합 정보"
  - "레코드 집합, 만들기"
  - "레코드 집합, 다이너셋"
  - "레코드 집합, 스냅샷"
  - "스냅샷, ODBC 레코드 집합"
ms.assetid: 333337c5-575e-4d26-b5f6-47166ad7874d
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 레코드 집합(ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 항목은 MFC ODBC 클래스에 적용됩니다.  
  
 [CRecordset](../../mfc/reference/crecordset-class.md) 개체는 데이터 소스에서 선택한 레코드 집합을 나타냅니다.  다음과 같은 데이터 소스에서 레코드를 선택할 수 있습니다.  
  
-   테이블  
  
-   쿼리  
  
-   하나 이상의 테이블에 액세스하는 저장 프로시저  
  
 테이블을 기반으로 하는 레코드 집합의 예로 Customer 테이블에 액세스하는 "모든 고객"이라는 레코드 집합을 만들 수 있습니다.  쿼리의 예로는 "Joe Smith의 모든 구매서"가 있습니다. 미리 정의된 쿼리라고도 하는 저장 프로시저를 기반으로 하는 레코드 집합의 예로 백 엔드 데이터베이스의 저장 프로시저를 호출하는 "연체된 계정"을 만들 수 있습니다.  레코드 집합은 동일한 데이터 소스의 테이블을 두 개 이상 조인할 수 있지만 서로 다른 데이터 소스의 테이블을 조인할 수는 없습니다.  
  
> [!NOTE]
>  마법사를 사용하여 레코드 집합 클래스를 파생시키는 방법은 [MFC ODBC 소비자 추가](../../mfc/reference/adding-an-mfc-odbc-consumer.md) 및 [MFC 응용 프로그램 마법사, 데이터베이스 지원](../../mfc/reference/database-support-mfc-application-wizard.md)을 참조하십시오.  
  
> [!NOTE]
>  일부 ODBC 드라이버는 데이터베이스 뷰를 지원합니다.  여기서 뷰는 원래 SQL `CREATE VIEW` 문으로 만든 쿼리를 말합니다.  현재 마법사에서는 뷰를 지원하지 않지만 뷰를 지원하도록 코드로 직접 작성할 수는 있습니다.  
  
##  <a name="_core_recordset_capabilities"></a> 레코드 집합 기능  
 모든 레코드 집합 개체에 다음과 같은 기능이 있습니다.  
  
-   데이터 소스가 읽기 전용이 아니면 레코드 집합을 [업데이트](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md), [추가](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md) 또는 읽기 전용으로 지정할 수 있습니다.  업데이트 가능한 레코드 집합인 경우 드라이버에서 적절한 잠금 지원 기능을 제공하면 비관적 또는 낙관적 [잠금](../../data/odbc/recordset-locking-records-odbc.md) 방법을 사용할 수 있습니다.  데이터 소스가 읽기 전용이면 레코드 집합도 읽기 전용입니다.  
  
-   멤버 함수를 호출하여 선택된 레코드를 [스크롤](../../data/odbc/recordset-scrolling-odbc.md)할 수 있습니다.  
  
-   레코드를 [필터](../../data/odbc/recordset-filtering-records-odbc.md)하여 사용 가능한 레코드에서 선택될 레코드를 제한할 수 있습니다.  
  
-   하나 이상의 열에서 오름차순 또는 내림차순으로 레코드를 [정렬](../../data/odbc/recordset-sorting-records-odbc.md)할 수 있습니다.  
  
-   레코드 집합을 [매개 변수화](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)하여 런타임에 선택될 레코드 집합을 제한할 수 있습니다.  
  
##  <a name="_core_snapshots_and_dynasets"></a> 스냅숏 및 다이너셋  
 [스냅숏](../../data/odbc/snapshot.md) 및 [다이너셋](../../data/odbc/dynaset.md)은 레코드 집합의 두 가지 기본 형식입니다.  `CRecordset` 클래스는 두 유형을 모두 지원합니다.  이러한 유형은 모든 레코드 집합의 공통 특징을 공유하지만 각기 고유한 방식으로 공통 기능을 확장하기도 합니다.  스냅숏은 데이터의 정적 뷰를 제공하며 보고서 또는 특정 시간대의 데이터 뷰를 필요로 하는 경우에 유용합니다.  반면에 다이너셋은 레코드 집합을 다시 쿼리하거나 새로 고치지 않고 다른 사용자가 업데이트한 레코드 집합 내용을 표시하려는 경우에 유용합니다.  스냅숏과 다이너셋은 업데이트할 수 있거나 읽기 전용입니다.  다른 사용자가 추가하거나 삭제한 레코드를 반영하려면 [CRecordset::Requery](../Topic/CRecordset::Requery.md)를 호출합니다.  
  
 또한 `CRecordset`에서는 동적 레코드 집합과 앞으로만 이동 가능한 레코드 집합 등 두 가지 레코드 집합을 사용할 수 있습니다.  동적 레코드 집합은 다이너셋과 유사하지만 `CRecordset::Requery`를 호출하지 않고 추가되거나 삭제된 모든 레코드를 반영합니다.  따라서 일반적으로 동적 레코드 집합은 DBMS에서 처리되는 시간이 길며 많은 ODBC 드라이버에서 지원되지 않습니다.  반면, 앞으로만 이동 가능한 레코드 집합을 사용하면 업데이트나 뒤로 스크롤할 필요가 없는 레코드 집합에서 가장 효율적으로 데이터에 액세스할 수 있습니다.  예를 들어, 데이터를 앞으로만 이동하는 데이터 소스 간에 데이터를 마이그레이션하는 데 앞으로만 이동 가능한 레코드 집합을 사용할 수 있습니다.  앞으로만 이동 가능한 레코드 집합을 사용하려면 다음과 같은 작업을 수행해야 합니다.  
  
-   옵션 **CRecordset::forwardOnly**를 [Open](../Topic/CRecordset::Open.md) 멤버 함수의 `nOpenType` 매개 변수로 전달합니다.  
  
-   **Open**의 `dwOptions` 매개 변수에 **CRecordset::readOnly**를 지정합니다.  
  
    > [!NOTE]
    >  다이너셋 지원에 필요한 ODBC 드라이버 요구 사항에 대한 자세한 내용은 [ODBC](../../data/odbc/odbc-basics.md)를 참조하십시오.  이 버전의 Visual C\+\+에 포함된 ODBC 드라이버 목록 및 추가 드라이버를 얻는 방법에 대한 내용은 [ODBC 드라이버 목록](../../data/odbc/odbc-driver-list.md)을 참조하십시오.  
  
##  <a name="_core_your_recordsets"></a> 사용자 레코드 집합  
 액세스하려는 모든 개별 테이블, 뷰 또는 저장 프로시저에 대해 일반적으로 `CRecordset`에서 파생된 클래스를 정의합니다. 이 경우 레코드 집합 하나가 둘 이상의 테이블에 있는 열을 나타내는 데이터베이스 조인은 예외입니다. 레코드 집합 클래스를 파생시킬 때 DDX\(대화 상자 데이터 교환\) 메커니즘과 유사한 Bulk RFX\(대량 레코드 필드 교환\) 메커니즘이나 RFX\(레코드 필드 교환\) 메커니즘을 사용합니다.  RFX 및 Bulk RFX 메커니즘을 사용하면 데이터 소스에서 레코드 집합으로 데이터를 간편하게 전송할 수 있습니다. RFX는 데이터를 레코드 집합에서 데이터 소스로 전송하는 기능도 제공합니다.  자세한 내용은 [RFX](../../data/odbc/record-field-exchange-rfx.md) 및 [레코드 집합: 대량 레코드 페치](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)를 참조하십시오.  
  
 레코드 집합 개체를 사용하여 모든 레코드에 액세스할 수 있도록 합니다.  `MoveNext`, `MovePrev` 같은 `CRecordset` 멤버 함수를 사용하여 선택된 여러 레코드를 스크롤합니다.  또한 레코드 집합 개체는 선택된 레코드 중 하나, 즉 현재 레코드만을 나타냅니다.  데이터베이스 쿼리의 결과 테이블이나 레코드의 열에 해당하는 레코드 집합 클래스 멤버 변수를 선언하여 현재 레코드의 필드를 검사할 수 있습니다.  레코드 집합 데이터 멤버에 대한 자세한 내용은 [레코드 집합: 아키텍처\(ODBC\)](../../data/odbc/recordset-architecture-odbc.md)를 참조하십시오.  
  
 레코드 집합 개체의 사용법에 대한 자세한 내용은 다음 항목에서 설명합니다.  이 항목은 기능별 범주로 나뉘어 순서대로 읽을 수 있도록 찾기 순서에 따라 나열되어 있습니다.  
  
### 레코드 집합 열기, 읽기 및 닫기에 관한 항목  
  
-   [레코드 집합: 아키텍처\(ODBC\)](../../data/odbc/recordset-architecture-odbc.md)  
  
-   [레코드 집합: 테이블에 대한 클래스 선언\(ODBC\)](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md)  
  
-   [레코드 집합: 레코드 집합 만들기 및 닫기\(ODBC\)](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md)  
  
-   [레코드 집합: 스크롤\(ODBC\)](../../data/odbc/recordset-scrolling-odbc.md)  
  
-   [레코드 집합: 책갈피와 절대 위치\(ODBC\)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)  
  
-   [레코드 집합: 레코드 필터링\(ODBC\)](../../data/odbc/recordset-filtering-records-odbc.md)  
  
-   [레코드 집합: 레코드 정렬\(ODBC\)](../../data/odbc/recordset-sorting-records-odbc.md)  
  
-   [레코드 집합: 레코드 집합 매개 변수화\(ODBC\)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)  
  
### 레코드 집합 수정 방법에 관한 항목  
  
-   [레코드 집합: 레코드 추가, 업데이트 및 삭제\(ODBC\)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)  
  
-   [레코드 집합: 레코드 잠금\(ODBC\)](../../data/odbc/recordset-locking-records-odbc.md)  
  
-   [레코드 집합: 레코드 집합 다시 쿼리\(ODBC\)](../../data/odbc/recordset-requerying-a-recordset-odbc.md)  
  
### 비교적 고급 기술에 관한 항목  
  
-   [레코드 집합: 조인 수행\(ODBC\)](../../data/odbc/recordset-performing-a-join-odbc.md)  
  
-   [레코드 집합: 미리 정의된 쿼리에 대한 클래스 선언\(ODBC\)](../../data/odbc/recordset-declaring-a-class-for-a-predefined-query-odbc.md)  
  
-   [레코드 집합: 데이터 열 동적 바인딩\(ODBC\)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)  
  
-   [레코드 집합: 대량 레코드 페치\(ODBC\)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)  
  
-   [레코드 집합: 대형 데이터 항목 작업\(ODBC\)](../../data/odbc/recordset-working-with-large-data-items-odbc.md)  
  
-   [레코드 집합: 합계 및 다른 집계 결과 구하기\(ODBC\)](../../data/odbc/recordset-obtaining-sums-and-other-aggregate-results-odbc.md)  
  
### 레코드 집합의 작동 방식에 관한 항목  
  
-   [레코드 집합: 레코드 집합의 레코드 선택 방법\(ODBC\)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)  
  
-   [레코드 집합: 레코드 집합의 레코드 업데이트 방법\(ODBC\)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)  
  
## 참고 항목  
 [ODBC\(Open Database Connectivity\)](../../data/odbc/open-database-connectivity-odbc.md)   
 [MFC ODBC 소비](../../mfc/reference/adding-an-mfc-odbc-consumer.md)   
 [트랜잭션\(ODBC\)](../../data/odbc/transaction-odbc.md)