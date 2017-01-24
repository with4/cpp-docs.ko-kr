---
title: "문서 및 뷰 작업 | Microsoft Docs"
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
  - "문서[C++], MFC"
  - "MFC[C++], 문서"
  - "MFC[C++], 뷰"
  - "뷰[C++], MFC"
ms.assetid: 349b142d-1c5a-4b99-9de4-241e41d3d2f1
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 문서 및 뷰 작업
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

MFC\(Microsoft Foundation Class\) 라이브러리의 기능 중 많은 부분이 문서\/뷰 아키텍처를 기반으로 합니다.  일반적으로 문서는 데이터를 저장하며, 뷰는 프레임 창의 클라이언트 영역에 데이터를 표시하고 사용자와 데이터 간 상호 작용을 관리합니다.  뷰는 문서와 통신하여 데이터를 가져오고 업데이트합니다.  데이터베이스 클래스는 프레임워크에서 사용하거나 단독으로 사용할 수 있습니다.  
  
 프레임워크에서 데이베이스 클래스를 사용하는 방법에 대한 자세한 내용은 [MFC: 문서 및 뷰를 이용한 데이터베이스 클래스 사용](../../data/mfc-using-database-classes-with-documents-and-views.md)을 참조하십시오.  
  
 기본적으로 MFC 응용 프로그램 마법사를 사용하여 만들어진 기초 응용 프로그램에는 데이터베이스 지원 기능이 포함되어 있지 않지만  필요하면 최소 데이터베이스 지원이나 좀더 완전한 폼 기반 지원 기능을 포함하도록 하는 옵션을 선택할 수 있습니다.  응용 프로그램 마법사 옵션에 대한 자세한 내용은 [MFC 응용 프로그램 마법사, 데이터베이스 지원](../../mfc/reference/database-support-mfc-application-wizard.md)을 참조하십시오.  
  
 전체 문서\/뷰 아키텍처를 사용하지 않고 데이터베이스 클래스를 사용할 수도 있습니다.  자세한 내용은 [MFC: 문서 및 뷰를 이용하지 않는 데이터베이스 클래스 사용](../../data/mfc-using-database-classes-without-documents-and-views.md)을 참조하십시오.  
  
## 참고 항목  
 [ODBC 및 MFC](../../data/odbc/odbc-and-mfc.md)