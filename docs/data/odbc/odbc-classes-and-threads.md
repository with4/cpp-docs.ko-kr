---
title: "ODBC 클래스와 스레드 | Microsoft Docs"
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
  - "ODBC 클래스, 스레드"
  - "ODBC, 다중 스레드 응용 프로그램"
  - "스레딩[MFC], ODBC 지원"
ms.assetid: 16543926-7331-41a6-ba50-72288f2a61b7
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ODBC 클래스와 스레드
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

MFC 4.2 버전부터는 MFC ODBC 클래스에 대한 다중 스레딩 지원이 제공됩니다.  그러나 MFC는 DAO 클래스에 대한 다중 스레딩 지원은 제공되지 않습니다.  
  
 ODBC 클래스에 대한 다중 스레딩 지원에는 일부 제한이 있습니다.  이 클래스는 ODBC API를 포함하기 때문에 그 기초가 되는 구성 요소에 대해서만 다중 스레딩 지원이 가능합니다.  예를 들어, 여러 ODBC 드라이버에는 스레드 안전성이 없으므로 이러한 드라이버 중 하나와 함께 MFC ODBC 클래스를 사용하면 스레드 안전성이 보장되지 않습니다.  따라서 사용하는 특정 드라이버가 스레드 안전인지 여부를 확인해야 합니다.  
  
 다중 스레드 응용 프로그램을 만들 때는 동일한 개체를 조작하는 다중 스레드 사용에 특히 주의해야 합니다.  예를 들어 두 스레드에서 동일한 `CRecordset` 개체를 사용하면 데이터를 검색할 때 문제가 발생할 수 있습니다. 즉, 한 스레드에 페치된 데이터가 다른 스레드에 페치된 데이터로 덮어쓰여질 수도 있습니다.  개별 스레드에서 MFC ODBC 클래스를 사용하는 좀더 일반적인 방법은 각 스레드에서 별도의 `CRecordset` 개체를 사용하고 열려 있는 `CDatabase` 개체를 스레드 간에 공유함으로써 동일한 ODBC 연결을 사용하는 것입니다.  열려 있지 않은 `CDatabase` 개체를 다른 스레드의 `CRecordset` 개체에 전달하지 않도록 주의해야 합니다.  
  
> [!NOTE]
>  여러 스레드가 같은 개체를 조작해야 하는 경우 임계 섹션과 같은 적절한 동기화 메커니즘을 구현해야 합니다.  **Open** 같은 특정 작업은 보호되지 않으므로  개별 스레드에서 동시에 이러한 작업이 호출되지 않도록 해야 합니다.  
  
 다중 스레드 응용 프로그램을 만드는 데 대한 자세한 내용은 [다중 스레딩 항목](../../parallel/multithreading-support-for-older-code-visual-cpp.md)을 참조하십시오.  
  
## 참고 항목  
 [ODBC\(Open Database Connectivity\)](../../data/odbc/open-database-connectivity-odbc.md)   
 [데이터 엑세스 프로그래밍 \(MFC\/ATL\)](../../data/data-access-programming-mfc-atl.md)