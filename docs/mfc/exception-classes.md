---
title: "예외 클래스 | Microsoft Docs"
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
  - "vc.classes.exception"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "예외 클래스"
  - "예외 처리, 예외 클래스"
  - "MFC, 예외"
ms.assetid: 1a2caf12-b3e9-4189-86d2-bf7a595bf025
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 예외 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

클래스 라이브러리는 클래스 `CException` 에 기반한 예외 처리 메커니즘을 제공합니다.  응용 프로그램 프레임 워크는 이 코드에서 예외를 사용합니다; 사용자 역시 이것을 사용할 수 있습니다.  자세한 내용은, [예외 처리](../mfc/exception-handling-in-mfc.md)를 참고하세요.  `CException` 으로부터 사용자 지정 예외 형식에서 파생 될 수 있습니다.  
  
 MFC는 이것을 지원하는 모든 예외클래스 뿐만아니라 파생될 수 있는 예외클래스까지 제공합니다.  
  
 [CException](../mfc/reference/cexception-class.md)  
 예외에 대한 기본 클래스입니다.  
  
 [CArchiveException](../mfc/reference/carchiveexception-class.md)  
 예외를 보관합니다.  
  
 [CDaoException](../mfc/reference/cdaoexception-class.md)  
 DAO 데이터베이스 작업에서 오류로 발생하는 예외입니다.  
  
 [CDBException](../mfc/reference/cdbexception-class.md)  
 ODBC 데이터베이스 처리 과정에서 오류가 발생한 예외입니다.  
  
 [CFileException](../mfc/reference/cfileexception-class.md)  
 파일 기반 예외입니다.  
  
 [CMemoryException](../mfc/reference/cmemoryexception-class.md)  
 out\-of\-memory 예외\[C\+\+\]  
  
 [CNotSupportedException](../mfc/reference/cnotsupportedexception-class.md)  
 지원되지 않은 기능을 사용함으로써 예외가 발생합니다.  
  
 [COleException](../mfc/reference/coleexception-class.md)  
 OLE 처리 과정에서 오류가 발생한 예외입니다.  이 클래스는 컨테이너와 서버, 두가지 모두 사용됩니다.  
  
 [COleDispatchException](../mfc/reference/coledispatchexception-class.md)  
 자동화하는 동안 오류에서 발생하는 예외입니다.  자동화 예외는 자동화 서버에서 발생되고, 자동화 클라이언트에서 발견됩니다.  
  
 [CResourceException](../mfc/reference/cresourceexception-class.md)  
 Windows 리소스를 로드하는 오류에서 발생한 예외입니다.  
  
 [CUserException](../mfc/reference/cuserexception-class.md)  
 사용자가 시작한 작업을 중지하는 데 사용 되는 예외입니다.  일반적으로, 이 예외를 발생하기 전에 사용자에게 문제가 알려집니다.  
  
## 참고 항목  
 [클래스 개요](../mfc/class-library-overview.md)