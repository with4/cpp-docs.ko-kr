---
title: "RFX | Microsoft Docs"
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
  - "데이터[MFC]"
  - "데이터[MFC], 소스 및 레코드 집합 간 이동"
  - "데이터베이스 클래스[C++], RFX"
  - "ODBC[C++], RFX"
  - "RFX(ODBC)[C++]"
ms.assetid: f5ddfbf0-2901-48d7-9848-4fb84de3c7ee
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# RFX
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

MFC ODBC 데이터베이스 클래스는 데이터 소스와 [레코드 집합](../../data/odbc/recordset-odbc.md) 개체 사이의 데이터 이동을 자동화합니다.  [CRecordset](../../mfc/reference/crecordset-class.md)에서 클래스를 파생시킬 때 대량 행 페치를 사용하지 않으면 RFX\(레코드 필드 교환\) 메커니즘에 의해 데이터가 전송됩니다.  
  
> [!NOTE]
>  파생된 `CRecordset` 클래스에서 대량 행 페치를 구현한 경우, 프레임워크는 Bulk RFX\(대량 레코드 필드 교환\) 메커니즘을 사용하여 데이터를 전송합니다.  자세한 내용은 [레코드 집합: 대량 레코드 페치\(ODBC\)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)를 참조하십시오.  
  
 RFX는 DDX\(대화 상자 데이터 교환\)와 유사합니다.  데이터 소스와 레코드 집합의 필드 데이터 멤버 간에 데이터를 이동하려면 레코드 집합의 [DoFieldExchange](../Topic/CRecordset::DoFieldExchange.md) 함수를 여러 번 호출해야 하며 프레임워크와 [ODBC](../../data/odbc/odbc-basics.md) 간에 많은 상호 작용이 필요합니다.  RFX 메커니즘은 형식이 안전한 메커니즘으로서 **::SQLBindCol**과 같은 ODBC 함수 호출 작업을 줄여줍니다.  DDX에 대한 자세한 내용은 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)를 참조하십시오.  
  
 RFX는 사용자에 대해 최대한의 투명성을 갖습니다.  [MFC ODBC 소비자 추가](../../mfc/reference/adding-an-mfc-odbc-consumer.md)에 설명된 대로 **클래스 추가** 또는 MFC 응용 프로그램 마법사를 사용하여 레코드 집합 클래스를 선언하면 해당 레코드 집합 클래스에 RFX가 자동으로 빌드됩니다.  레코드 집합 클래스는 프레임워크에서 제공하는 기본 클래스인 `CRecordset`에서 파생되어야 합니다.  MFC 응용 프로그램 마법사를 사용하면 초기 레코드 집합 클래스를 만들 수 있습니다.  또한 **클래스 추가**를 사용하면 필요할 때마다 레코드 집합 클래스를 더 추가할 수 있습니다.  자세한 내용 및 예제는 [MFC ODBC 소비자 추가](../../mfc/reference/adding-an-mfc-odbc-consumer.md)를 참조하십시오.  
  
 다음 3가지 경우에는 약간의 RFX 코드를 직접 작성해야 합니다.  
  
-   매개 변수가 있는 쿼리를 사용하려는 경우:  자세한 내용은 [레코드 집합: 레코드 집합 매개 변수화\(ODBC\)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)를 참조하십시오.  
  
-   2개 이상의 테이블에 있는 열에 대해 단일 레코드 집합을 사용하여 조인을 수행하려는 경우:  자세한 내용은 [레코드 집합: 조인 수행\(ODBC\)](../../data/odbc/recordset-performing-a-join-odbc.md)을 참조하십시오.  
  
-   데이터 열을 동적으로 바인딩하려는 경우:  매개 변수화에 비해 덜 일반적인 경우입니다.  자세한 내용은 [레코드 집합: 데이터 열 동적 바인딩\(ODBC\)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)을 참조하십시오.  
  
 RFX에 대한 자세한 내용은 [레코드 필드 교환: RFX 작동 방식](../../data/odbc/record-field-exchange-how-rfx-works.md)을 참조하십시오.  
  
 레코드 집합 개체의 사용법에 대한 자세한 내용은 다음 문서에서 설명합니다.  
  
-   [레코드 필드 교환: RFX 사용](../../data/odbc/record-field-exchange-using-rfx.md)  
  
-   [레코드 필드 교환: RFX 함수 사용](../../data/odbc/record-field-exchange-using-the-rfx-functions.md)  
  
-   [레코드 필드 교환: RFX 작동 방식](../../data/odbc/record-field-exchange-how-rfx-works.md)  
  
## 참고 항목  
 [ODBC\(Open Database Connectivity\)](../../data/odbc/open-database-connectivity-odbc.md)   
 [레코드 집합\(ODBC\)](../../data/odbc/recordset-odbc.md)   
 [MFC ODBC 소비](../../mfc/reference/adding-an-mfc-odbc-consumer.md)   
 [MFC 응용 프로그램 마법사, 데이터베이스 지원](../../mfc/reference/database-support-mfc-application-wizard.md)   
 [CRecordset Class](../../mfc/reference/crecordset-class.md)