---
title: "DAO 클래스 | Microsoft Docs"
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
  - "vc.classes.data"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DAO[C++], 클래스"
  - "데이터베이스 클래스[C++], DAO"
ms.assetid: b15d0cd6-328b-4288-9c19-d037a795db57
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# DAO 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

These classes work with the other application framework classes to give easy access to Data Access Object \(DAO\) databases, which use the same database engine as Microsoft Visual Basic and Microsoft Access.  The DAO classes can also access a wide variety of databases for which Open Database Connectivity \(ODBC\) drivers are available.  
  
 Programs that use DAO databases will have at least a `CDaoDatabase` object and a `CDaoRecordset` object.  
  
> [!NOTE]
>  Visual C\+\+ .NET에서는 포함된 DAO 클래스를 아직 사용할 수 있지만 Visual C\+\+ 환경 및 마법사가 더 이상 DAO를 지원하지 않습니다.  Microsoft recommends that you use ODBC for new MFC projects.  DAO는 기존 응용 프로그램을 유지 관리하는 데만 사용할 수 있습니다.  
  
 [CDaoWorkspace](../mfc/reference/cdaoworkspace-class.md)  
 Manages a named, password\-protected database session from login to logoff.  Most programs use the default workspace.  
  
 [CDaoDatabase](../mfc/reference/cdaodatabase-class.md)  
 A connection to a database through which you can operate on the data.  
  
 [CDaoRecordset](../mfc/reference/cdaorecordset-class.md)  
 데이터 소스에서 선택한 레코드 집합을 나타냅니다.  
  
 [CDaoRecordView](../mfc/reference/cdaorecordview-class.md)  
 컨트롤에 데이터베이스 레코드를 표시하는 뷰입니다.  
  
 [CDaoQueryDef](../mfc/reference/cdaoquerydef-class.md)  
 Represents a query definition, usually one saved in a database.  
  
 [CDaoTableDef](../mfc/reference/cdaotabledef-class.md)  
 기본 테이블 또는 연결된 테이블의 저장된 정의를 나타냅니다.  
  
 [CDaoException](../mfc/reference/cdaoexception-class.md)  
 Represents an exception condition arising from the DAO classes.  
  
 [CDaoFieldExchange](../mfc/reference/cdaofieldexchange-class.md)  
 DAO 데이터베이스 클래스에서 사용하는 DAO 레코드 필드 교환\(DFX\) 루틴을 지원합니다.  You will normally not directly use this class.  
  
## Related Classes  
 [CLongBinary](../mfc/reference/clongbinary-class.md)  
 Encapsulates a handle to storage for a binary large object \(BLOB\), such as a bitmap.  `CLongBinary` objects are used to manage large data objects stored in database tables.  
  
 [COleCurrency](../mfc/reference/colecurrency-class.md)  
 Wrapper for the OLE automation type **CURRENCY**, a fixed\-point arithmetic type, with 15 digits before the decimal point and 4 digits after.  
  
 [COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md)  
 Wrapper for the OLE automation type **DATE**.  Represents date and time values.  
  
 [COleVariant](../mfc/reference/colevariant-class.md)  
 Wrapper for the OLE automation type **VARIANT**.  Data in **VARIANT**s can be stored in many formats.  
  
## 참고 항목  
 [클래스 개요](../mfc/class-library-overview.md)