---
title: "TN055: MFC ODBC 데이터베이스 클래스 응용 프로그램을 MFC DAO 클래스로 마이그레이션 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.odbc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DAO[C++], 마이그레이션"
  - "데이터베이스 응용 프로그램 마이그레이션"
  - "ODBC 데이터베이스 응용 프로그램 마이그레이션"
  - "마이그레이션[C++], ODBC 데이터베이스 응용 프로그램"
  - "ODBC[C++], DAO"
  - "ODBC 클래스[C++], DAO 클래스"
  - "DAO로 데이터베이스 응용 프로그램 이식"
  - "DAO로 ODBC 데이터베이스 응용 프로그램 이식"
  - "TN055"
ms.assetid: 0f858bd1-e168-4e2e-bcd1-8debd82856e4
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# TN055: MFC ODBC 데이터베이스 클래스 응용 프로그램을 MFC DAO 클래스로 마이그레이션
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Visual C\+\+ .NET에서는 포함된 DAO 클래스를 아직 사용할 수 있지만 Visual C\+\+ 환경 및 마법사가 더 이상 DAO를 지원하지 않습니다.  Microsoft는 새 프로젝트에 대해 [OLE DB Templates](../data/oledb/ole-db-templates.md)이나 [ODBC and MFC](../data/odbc/odbc-and-mfc.md)를 사용할 것을 권장합니다.  DAO는 기존 응용 프로그램을 유지 관리하는 데만 사용할 수 있습니다.  
  
 **개요**  
  
 대부분의 경우 MFC의 ODBC 데이터베이스 클래스를 사용하는 응용 프로그램을 MFC의 DAO 데이터베이스 클래스로 변경하는 것이 바람직할 수 있습니다.  이 기술 노트는 MFC ODBC와 DAO 클래스의 대부분의 차이를 자세히 설명할 것입니다.  차이를 염두에 두어, 원한다면 응용 프로그램을 ODBC 클래스에서 MFC 클래스로 바꾸는 것이 너무 어렵지 않도록 해야 합니다.  
  
 **왜 ODBC에서 DAO로 변경합니까?**  
  
 사용자가 응용 프로그램을 ODBC 데이터베이스 클래스에서 DAO 데이터베이스 클래스로 변경하는 것을 원할 수 있는 이유는 여러 가지가 있지만, 결정은 반드시 간단하거나 명백하지는 않습니다.  한가지 유념해 두어야 할 것은 DAO에 의해 사용되는 Microsoft Jet 데이터베이스 엔진은 사용자가 해당 ODBC 드라이버를 보유한 ODDB 데이터 소스를 읽을 수 있다는 것입니다.  ODBC 데이터베이스 클래스를 사용하거나 ODBC를 사용자가 직접 호출하는 것이 좀 더 효율적일 수 있지만, Microsoft Jet 데이터베이스 엔진은 ODBC 데이터를 읽을 수 있습니다.  
  
 ODBC\/DAO 결정을 쉽게 만드는 몇 가지 간단한 사례들은,  예를 들어, 사용자가 Microsoft Jet 엔진이 직접 읽을 수 있는\(Access, Excel 형식 등\) 형식에서, 데이터에 접근하는 것만을 원할 때에는, DAO 데이터베이스 클래스를 사용하는 것이 확실한 선택입니다.  
  
 데이터가 하나의 서버 또는 여러가지 서버에 있는 경우, 보다 복잡한 경우가 발생합니다.  이 경우, ODBC 데이터베이스 클래스를 사용할지 DAO 데이터베이스 클래스를 사용할지 결정하는 것은 어렵습니다.  사용자가 이질적인 조인\(SQL Server나 Oracle같은 다양한 형식의 서버로부터 데이터를 조인하는 것\)같은 것을 하기 원하면, 사용자가 ODBC 데이터베이스 클래스를 사용하거나 ODBC를 직접 호출하는 경우에, Microsoft Jet 데이터베이스 엔진은 사용자가 필요한 작업을 수행하게 강제하는 대신에 사용자를 위해 조인을 수행할 것입니다.  드라이버 커서를 지원하는 ODBC 드라이버를 사용하면, ODBC 데이터베이스 클래스를 사용하는 것이 가장 좋은 선택일 수 있습니다.  
  
 이 선택은 복잡해질 수 있으므로, 사용자는 사용자의 특별한 필요에 의한 다양한 방법의 성능을 테스트하기 위해 샘플 코드를 작성하는 것을 원할 수 있습니다.  이 기술 노트는 사용자가 ODBC 데이터베이스 클래스를 DAO 데이터베이스 클래스로 변경하는 것으로 결정했다고 가정합니다.  
  
 **ODBC 데이터베이스 클래스와 MFC DAO 데이터베이스 클래스 간의 유사점**  
  
 MFC ODBC 클래스의 원안은 Microsoft Access 및 Microsoft Visual Basic에서 사용되는 DAO 개체 모델을 기반으로 합니다.  이것은 ODBC 및 DAO MFC 클래스가 많은 공통점이 있다는 것을 의미합니다. 그것은 여기에서 모두 나열되지는 않습니다.  일반적으로, 프로그래밍 모델은 동일합니다.  
  
 몇 가지 유사점을 강조합니다.  
  
-   ODBC와 DAO 클래스는 모두 기본 데이터베이스 관리 시스템\(DBMS\)을 관리하는 데이터베이스 개체를 가집니다.  
  
-   둘 다 DBMS에서 반환된 결과 집합을 나타내는 레코드 집합 개체를 가집니다.  
  
-   DAO 데이터베이스 및 레코드 집합 개체는 ODBC 클래스와 거의 동일한 멤버를 가집니다.  
  
-   두 클래스 집합을 사용하여, 데이터를 검색하는 코드는 일부 개체와 멤버 이름 변경을 제외하고 동일합니다.  변경이 필요할 수 있지만, ODBC 클래스에서 DAO 클래스로 전환할 때 이름 변경은 보통 간단합니다.  
  
 예를 들어, 두 모델에서 데이터를 검색하는 절차는 데이터베이스 개체를 생성하거나 열고, 레코드 집합 개체를 생성하거나 열고, 몇 가지 작업을 수행하는 데이터로 이동하는 것입니다.  
  
 **ODBC와 DAO MFC 클래스의 차이점**  
  
 DAO 클래스는 더 많은 개체와 메서드 집합을 포함하지만, 이 세션에서는 유사한 클래스와 기능의 차이점만 자세히 설명합니다.  
  
 아마도 클래스간의 가장 명백한 차이점은 유사한 클래스와 전역 함수를 위해 변경되는 이름입니다.  다음 목록은 개체의 이름 변경, 메서드 및 데이터베이스 클래스와 관련된 전역 함수를 보여줍니다.  
  
|클래스 또는 함수|MFC DAO 클래스와 동일|  
|---------------|---------------------|  
|`CDatabase`|`CDaoDatabase`|  
|`CDatabase::ExecuteSQL`|`CDaoDatabase::Execute`|  
|`CRecordset`|`CDaoRecordset`|  
|`CRecordset::GetDefaultConnect`|`CDaoRecordset::GetDefaultDBName`|  
|`CFieldExchange`|`CDaoFieldExchange`|  
|`RFX_Bool`|`DFX_Bool`|  
|`RFX_Byte`|`DFX_Byte`|  
|`RFX_Int`|`DFX_Short`|  
|`RFX_Long`|`DFX_Long`|  
||`DFX_Currency`|  
|`RFX_Single`|`DFX_Single`|  
|`RFX_Double`|`DFX_Double`|  
|**RFX\_Date \***|**DFX\_Date** \(`COleDateTime`\-based\)|  
|`RFX_Text`|`DFX_Text`|  
|`RFX_Binary`|`DFX_Binary`|  
|`RFX_LongBinary`|`DFX_LongBinary`|  
  
 \*    `RFX_Date` 함수는 `CTime` 및 **TIMESTAMP\_STRUCT**를 기반으로 합니다.  
  
 사용자 응용 프로그램에 영향을 미칠 수 있거나 아래에 나열된 좀 더 간단한 이름 변경이 요구되는 주요 변경 기능  
  
-   상수와 매크로는 변경된 레코드 집합 열기 형식 및 레코드 집합 열기 옵션같은 것을 지정하는데 쓰입니다.  
  
     ODBC 클래스를 포함한 MFC는 이러한 옵션을 매크로 또는 열거 형식을 이용하여 정의할 필요가 있습니다.  
  
     DAO 클래스를 사용하여, DAO는 헤더 파일\(DBDAOINT.H\)에서 이러한 옵션의 정의를 제공합니다.  따라서 레코드 집합 형식은 `CRecordset`의 열거된 멤버입니다. 그러나 대신에, DAO를 사용하면 이는 상수입니다.  예를 들어 ODBC에서 `CRecordset`의 형식을 지정할 때  **snapshot**을 사용합니다. 그러나 `CDaoRecordset`의 형식을 지정할 때는 **DB\_OPEN\_SNAPSHOT**을 사용합니다.  
  
-   `CRecordset`를 위한 기본 레코드 집합 형식은 `CDaoRecordset`를 위한 기본 레코드 집합 형식이 **dynaset**인 동안 **snapshot**입니다. \(ODBC 클래스 스냅샷에 대한 추가 문제는 아래 참고를 참조하십시오\)  
  
-   ODBC `CRecordset` 클래스는 forward\-only 레코드 집합 형식을 생성하는 옵션을 가집니다.  `CDaoRecordset` 클래스에서, forward\-only는 레코드 집합 형식이라기 보다는 레코드집합의 특정 형식의 속성\(또는 옵션\)입니다.  
  
-   `CRecordset` 개체를 열 때 append\-only 레코드 집합은 읽혀지거나 추가될 수 있는 레코드 집합의 데이터를 의미합니다.  `CDaoRecordset` 개체를 사용한 첨부 전용 옵션은 문자 그대로 추가될 수 있는\(그리고 읽힐 수 없는\) 레코드 집합의 데이터를 의미합니다.  
  
-   ODBC 클래스의 트랜잭션 멤버 함수는 `CDatabase`의 멤버이고 데이터베이스 레벨에서 수행됩니다.  DAO 클래스에서, 트랜잭션 멤버 함수는 더 높은 레벨 클래스의 멤버이고\(`CDaoWorkspace`\) 따라서 같은 작업장\(트랜잭션 공간\)을 공유하는 많은 `CDaoDatabase` 개체에 영향을 미칠 것입니다.  
  
-   예외 클래스가 변경되었습니다.  ODBC 클래스에서는 **CDBExceptions**가 발생하고 DAO 클래스에서는 **CDaoExceptions**가 발생합니다.  
  
-   `RFX_Date`는  **DFX\_Date**가 `COleDateTime`을 사용하는 동안 `CTime` 및 **TIMESTAMP\_STRUCT** 개체를 사용합니다.  `COleDateTime`는 거의 `CTime`와 비슷합니다. 그러나 4바이트 `time_t`보다는 8 바이트 OLE **DATE**를 기반으로 합니다. 그래서 훨씬 더 큰 데이터 범위를 저장할 수 있습니다.  
  
    > [!NOTE]
    >  ODBC\(`CRecordset`\) 스냅샷이 드라이버와 ODBC 커서 라이브러리 사용에 따라 업데이트가 가능한 반면, DAO\(`CDaoRecordset`\) 스냅샷은 읽기 전용입니다.  커서 라이브러리를 사용하는 경우 `CRecordset` 스냅샷이 업데이트할 수 있습니다.  ODBC 커서 라이브러리 없이 데스크톱 드라이버 팩 3.0에서 Microsoft 드라이버 중 어떤 것을 사용중인 경우, `CRecordset` 스냅샷은 읽기 전용입니다.  다른 드라이버를 사용하는 경우, 스냅샷\(**STATIC\_CURSORS**\)이 읽기 전용이라면 참조할 드라이버 설명서를 확인하세요.  
  
## 참고 항목  
 [번호별 기술 참고 사항](../mfc/technical-notes-by-number.md)   
 [범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)