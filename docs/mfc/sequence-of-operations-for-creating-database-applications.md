---
title: "데이터베이스 응용 프로그램을 만드는 작업 시퀀스 | Microsoft Docs"
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
  - "응용 프로그램[MFC], 데이터베이스"
  - "데이터베이스 응용 프로그램[C++]"
  - "데이터베이스 응용 프로그램[C++], 만들기"
  - "MFC[C++], 데이터베이스 응용 프로그램"
ms.assetid: 9371da59-8536-43cd-8314-706ad320e2ec
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 데이터베이스 응용 프로그램을 만드는 작업 시퀀스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The following table shows your role and the framework's role in writing database applications.  
  
> [!NOTE]
>  Visual C\+\+ .NET에서는 포함된 DAO 클래스를 아직 사용할 수 있지만 Visual C\+\+ 환경 및 마법사가 더 이상 DAO를 지원하지 않습니다.  Microsoft recommends that you use ODBC for new MFC projects.  DAO는 기존 응용 프로그램을 유지 관리하는 데만 사용할 수 있습니다.  
  
### Creating Database Applications  
  
|Task|You do|The framework does|  
|----------|------------|------------------------|  
|Decide whether to use the MFC ODBC or DAO classes.|Use ODBC for new MFC projects.  Use DAO only to maintain existing applications.  See [Should I use DAO or ODBC?](../data/should-i-use-dao-or-odbc-q.md).  For general information, see the article [Data Access Programming](../data/data-access-programming-mfc-atl.md).|The framework supplies classes that support database access.|  
|Create your skeleton application with database options.|Run the MFC Application Wizard.  Select options on the Database Support page.  If you choose an option that creates a record view, also specify:<br /><br /> -   Data source and table name or names<br />-   Query name or names.|The MFC Application Wizard creates files and specifies the necessary includes.  Depending on the options you specify, the files can include a recordset class.|  
|Design your database form or forms.|Use the Visual C\+\+ dialog editor to place controls on the dialog template resources for your record view classes.|The MFC Application Wizard creates an empty dialog template resource for you to fill in.|  
|Create additional record view and recordset classes as needed.|Use Class View to create the classes and the dialog editor to design the views.|Class View creates additional files for your new classes.|  
|Create recordset objects as needed in your code.  Use each recordset to manipulate records...|Your recordsets are based on the classes derived from [CRecordset](../mfc/reference/crecordset-class.md) with the wizards.|ODBC uses record field exchange \(RFX\) to exchange data between the database and your recordset's field data members.  If you are using a record view, dialog data exchange \(DDX\) exchanges data between the recordset and the controls on the record view.|  
|...or create an explicit [CDatabase](../mfc/reference/cdatabase-class.md) in your code for each database you want to open.|Base your recordset objects on the database objects.|The database object provides an interface to the data source.|  
|Bind data columns to your recordset dynamically.|In ODBC, add code to your derived recordset class to manage the binding.  See the article [Recordset: Dynamically Binding Data Columns \(ODBC\)](../data/odbc/recordset-dynamically-binding-data-columns-odbc.md).||  
  
## 참고 항목  
 [프레임워크를 기반으로 구축](../mfc/building-on-the-framework.md)   
 [MFC 응용 프로그램을 빌드하는 작업 시퀀스](../mfc/sequence-of-operations-for-building-mfc-applications.md)   
 [OLE 응용 프로그램을 만드는 작업 시퀀스](../mfc/sequence-of-operations-for-creating-ole-applications.md)   
 [ActiveX 컨트롤을 만드는 작업 시퀀스](../mfc/sequence-of-operations-for-creating-activex-controls.md)