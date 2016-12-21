---
title: "데이터 엑세스 프로그래밍 (MFC/ATL) | Microsoft Docs"
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
  - "데이터[C++], 데이터 액세스 기술"
  - "데이터 액세스[C++], 데이터베이스용 클래스 라이브러리"
  - "데이터베이스[C++], MFC"
  - "MFC[C++], 데이터 액세스 응용 프로그램"
  - "OLE DB[C++], 데이터 액세스 기술"
ms.assetid: def97b2c-b5a6-445f-afeb-308050fd4852
caps.latest.revision: 14
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 데이터 엑세스 프로그래밍 (MFC/ATL)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+는 데이터베이스를 사용하여 작업하는 여러 가지 방법을 제공합니다.  기본적으로는 ATL\(액티브 템플릿 클래스 라이브러리\) 또는 MFC\(Microsoft Foundation Class\) 라이브러리와 같은 클래스 라이브러리 중 하나를 사용합니다. 따라서 데이터베이스 API를 간편하게 사용할 수 있습니다.  
  
> [!NOTE]
>  이 항목에서는 Visual C\+\+의 데이터베이스 응용 프로그램에 사용할 수 있는 기존 기술에 대해 설명합니다.  Visual C\+\+ 및 SQL Server 2005를 사용하는 데이터 액세스 프로그래밍에 대한 자세한 내용은 [데이터 액세스](../dotnet/data-access-using-adonet-cpp-cli.md), [Visual Studio에서 데이터 액세스](../Topic/Accessing%20data%20in%20Visual%20Studio.md) 및 [Creating SQL Server 2005 Objects In Managed Code](http://msdn.microsoft.com/ko-kr/5358a825-e19b-49aa-8214-674ce5fed1da)를 참조하세요.  
  
 라이브러리 클래스는 다음과 같은 종류의 데이터 액세스를 지원합니다.  
  
-   ATL은 OLE DB 템플릿 및 데이터베이스 특성을 제공합니다.  
  
-   MFC는 ODBC\(Open Database Connectivity\) 및 ODBC 드라이버를 제공합니다.  
  
 이러한 라이브러리는 C\+\+의 빠른 속도와 효율적인 기능 및 유동성을 완벽하게 제공하여 데이터베이스를 간편하게 사용할 수 있도록 하는 추상화를 제공하며  데이터 액세스 작업을 라이브러리의 응용 프로그램 프레임워크에 통합합니다.  
  
 COM, ODBC 또는 DAO SDK\(소프트웨어 개발 키트\)에서 데이터베이스 API 함수를 직접 호출할 수도 있습니다.  COM, DAO 또는 ODBC API 함수를 사용하여 직접 프로그래밍하는 방법에 대한 자세한 내용은 COM SDK, DAO SDK 또는 ODBC SDK를 참조하세요.  
  
 데이터가 저장되는 폼에 관계없이 데이터에 액세스해야 하는 경우에는 ATL OLE DB를 사용합니다.  Microsoft Jet\(.mdb\) 데이터베이스를 사용 중이지 않으며 완전한 데이터 소스 독립성을 위해 ODBC API를 사용하려는 경우에는 MFC ODBC 클래스를 사용합니다.  ODBC 데이터 소스와 같은 외부 데이터베이스 또는 Microsoft Jet\(.mdb\) 데이터베이스를 사용하려는 경우에는 MFC DAO 클래스를 사용합니다.  
  
> [!NOTE]
>  새 프로젝트의 경우에는 OLE DB 또는 ODBC를 사용하는 것이 좋습니다.  DAO는 기존 응용 프로그램 유지 관리에만 사용해야 합니다.  
  
 독립 실행형 데이터베이스 응용 프로그램 외에 다른 종류의 프로그램에서도 편리한 저장소 및 검색 매체로 데이터베이스를 효율적으로 사용할 수 있는 경우가 많습니다.  
  
|자세한 정보를 확인할 항목|참조|  
|--------------------|--------|  
|**데이터베이스 기술 선택**||  
|비교: ODBC와  DAO|[DAO와 ODBC를 사용해야 합니까?](../data/should-i-use-dao-or-odbc-q.md)|  
|Microsoft 기술 자료를 사용하여 제품 지원 엔지니어가 작성한 데이터베이스 항목에 대한 추가 문서 찾기|[Microsoft 기술 자료](../data/where-can-i-find-microsoft-knowledge-base-articles-on-database-topics-q.md)|  
|**ATL 데이터베이스 지원\(OLE DB\)**||  
|OLE DB 프로그래밍\(개념 항목\)|[OLE DB 프로그래밍 개요](../data/oledb/ole-db-programming-overview.md)|  
|OLE DB 소비자 템플릿 사용\(개념 항목\)|[OLE DB 소비자 템플릿](../data/oledb/ole-db-consumer-templates-cpp.md)|  
|OLE DB 소비자 특성|[OLE DB 소비자 특성](../windows/ole-db-consumer-attributes.md)|  
|OLE DB 공급자 템플릿 사용\(개념 항목\)|[OLE DB 공급자 템플릿](../data/oledb/ole-db-provider-templates-cpp.md)|  
|MFC 프로젝트에 OLE DB 소비자 추가|[OLE DB 소비자 만들기](../data/oledb/creating-an-ole-db-consumer.md)|  
|**MFC 데이터베이스 지원\(ODBC 및 DAO\)**||  
|DAO와 ODBC의 정의|[DAO와 ODBC란 무엇입니까?](../data/what-are-dao-and-odbc-q.md)|  
|MFC 데이터베이스 클래스를 사용하는 경우|[데이터베이스 클래스를 사용하는 시기는 언제입니까?](../data/when-should-i-use-the-database-classes-q.md)|  
|MFC 데이터베이스 프로그래밍 모델에 대한 자세한 정보|[MFC 데이터베이스 프로그래밍 모델은 무엇입니까?](../data/what-is-the-mfc-database-programming-model-q.md).|  
|MFC DAO 클래스와 MFC ODBC 클래스 중에서 선택|[DAO와 ODBC를 사용해야 합니까?](../data/should-i-use-dao-or-odbc-q.md).|  
|DAO 및 ODBC를 사용하여 액세스할 수 있는 데이터 소스|[DAO와 ODBC를 사용하여 액세스할 수 있는 데이터 소스는 무엇입니까?](../data/what-data-sources-can-i-access-with-dao-and-odbc-q.md)|  
|ODBC\(Open Database Connectivity\)|[ODBC 및 MFC](../data/odbc/odbc-and-mfc.md)|  
|클래스를 사용하면서 DAO 또는 ODBC API를 직접 호출할 수 있는지 여부|[DAO나 ODBC를 직접 호출할 수 있습니까?](../data/can-i-call-dao-or-odbc-directly-q.md)|  
|제공되는 ODBC 드라이버|[ODBC 드라이버 목록](../data/odbc/odbc-driver-list.md)|  
|데이터베이스 클래스가 MFC 문서\/뷰 아키텍처를 사용하는 방식|[MFC: 문서 및 뷰를 이용한 데이터베이스 클래스 사용](../data/mfc-using-database-classes-with-documents-and-views.md)|  
|MFC 데이터베이스 지원 설치\/Visual C\+\+에서 기본적으로 설치되는 ODBC 드라이버\/설치되는 ODBC 및 DAO SDK 구성 요소|[MFC 데이터베이스 지원 설치](../data/installing-mfc-database-support.md)|  
|**데이터 바인딩된 컨트롤\(ADO 및 RDO\)**||  
|데이터 바인딩된 컨트롤을 사용하는 프로그램 작성|[데이터 바인딩된 컨트롤\(ADO 및 RDO\)](../data/ado-rdo/data-bound-controls-ado-and-rdo.md)|  
|ActiveX 컨트롤을 사용한 데이터 바인딩|[MFC ActiveX 컨트롤: ActiveX 컨트롤에서 데이터 바인딩 사용](../mfc/mfc-activex-controls-using-data-binding-in-an-activex-control.md)|  
|ActiveX 컨트롤 배포|[MFC ActiveX 컨트롤: ActiveX 컨트롤 배포](../mfc/mfc-activex-controls-distributing-activex-controls.md)|  
  
## 참고 항목  
 [데이터 액세스](../Topic/Data%20Access%20in%20Visual%20C++.md)