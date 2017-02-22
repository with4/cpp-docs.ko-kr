---
title: "OLE DB 아키텍처 설계 문제 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OLE DB, 응용 프로그램 디자인 고려 사항"
ms.assetid: 8caa7d99-d2bb-42c9-8884-74f228bb6ecc
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# OLE DB 아키텍처 설계 문제
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OLE DB 응용 프로그램을 시작하기 전에 먼저 다음 문제에 대해 고려해야 합니다.  
  
 **OLE DB 응용 프로그램을 작성하기 위해 어떤 프로그래밍 구현을 사용할 예정입니까?**  
 Microsoft에서는 이러한 구현을 위해 OLE DB 템플릿 라이브러리, OLE DB 특성, OLE DB SDK의 원시 OLE DB 인터페이스 같은 여러 라이브러리를 제공하고 있습니다.  또한 프로그램 작성에 도움이 되는 마법사도 제공됩니다.  이러한 구현에 대해 [OLE DB 템플릿, 특성 및 기타 구현](../../data/oledb/ole-db-templates-attributes-and-other-implementations.md)에서 설명합니다.  
  
 **스스로 공급자를 작성해야 합니까?**  
 대부분의 개발자는 고유한 공급자를 직접 작성할 필요가 없습니다.  Microsoft에서는 여러 공급자를 제공하고 있습니다.  예를 들어, 데이터 연결을 만들 때마다 ATL OLE DB 소비자 마법사를 사용하여 프로젝트에 소비자를 추가할 때, **데이터 연결 속성** 대화 상자에는 시스템에 등록된 사용할 수 있는 모든 공급자의 목록이 나타나게 됩니다.  이들 공급자 중 하나가 데이터 저장소와 데이터 액세스 응용 프로그램에 알맞은 경우에는 간단하게 해당 공급자를 사용하면 됩니다.  그러나 데이터 저장소가 이들 카테고리 중 하나에 맞지 않은 경우에는 스스로 공급자를 만들어야 합니다.  공급자를 만드는 데 대한 자세한 내용은 [OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)을 참조하십시오.  
  
 **소비자에 대해서는 어떤 수준의 지원이 필요합니까?**  
 어떤 소비자는 매우 기본적이고 어떤 소비자는 매우 복잡할 수 있습니다.  OLE DB 개체의 기능은 속성에 의해 지정됩니다.  ATL OLE DB 소비자 마법사를 사용하여 소비자를 만들거나 데이터베이스 공급자 마법사를 사용하여 공급자를 만들 때, 기능의 표준 집합을 제공하기 위해 사용자에게 알맞은 개체 속성을 설정합니다.  그러나 사용자가 원하는 모든 작업을 마법사로 생성된 소비자 및 공급자 클래스가 지원하지 않을 경우에는 [OLE DB 템플릿 라이브러리](../../data/oledb/ole-db-templates.md)에서 해당 클래스에 대한 인터페이스를 참조해야 합니다.  이들 인터페이스는 쉬운 원시 OLE DB 인터페이스를 사용하여 여분의 구현을 제공하면서, 원시 OLE DB 인터페이스를 래핑합니다.  
  
 예를 들어, 행 집합의 데이터를 업데이트하려고 하지만 마법사로 소비자를 만들었을 때 기능을 지정하는 것을 잊은 경우, 명령 개체에서 **DBPROP\_IRowsetChange** 및 **DBPROP\_UPDATABILITY** 속성을 설정하여 팩트 후에 기능을 지정할 수 있습니다.  그러면 행 집합이 작성되었을 때 `IRowsetChange` 인터페이스를 갖게 됩니다.  
  
 **Do you have older code using another data access technology \(ADO, ODBC, or DAO\)?**  
 기술의 조합\(ADO 구성 요소를 OLE DB 구성 요소와 함께 사용하거나, ODBC 코드를 OLE DB에 마이그레이션하는 등\)을 가정하여 볼 때 Visual C\+\+ 설명서만으로는 모든 상황에 대해 설명할 수 없습니다.  그러나 다음 Microsoft 웹 사이트에서 다양한 시나리오에 대한 많은 기사를 참조할 수 있습니다.  
  
-   [Microsoft Help and Support](http://go.microsoft.com/fwlink/?LinkId=148218)  
  
-   [Microsoft Data Access Technical Articles Overview](http://go.microsoft.com/fwlink/?LinkId=148217)  
  
-   [Visual Studio Solution Center](http://go.microsoft.com/fwlink/?LinkId=148215)  
  
-   [Search Microsoft.com](http://search.microsoft.com/)  
  
 검색을 수행하려면 시나리오에 가장 알맞은 키워드 조합을 입력하십시오. 예를 들어 OLE DB 공급자에서 ADO 개체를 사용하는 경우에는 **ADO AND "OLE DB"**로 부울 검색을 시도하십시오.  If you wanted to migrate older DAO code to ODBC, select "all words" and specify strings such as **migrating DAO**.  
  
## 참고 항목  
 [OLE DB 프로그래밍](../../data/oledb/ole-db-programming.md)   
 [OLE DB 프로그래밍 개요](../../data/oledb/ole-db-programming-overview.md)