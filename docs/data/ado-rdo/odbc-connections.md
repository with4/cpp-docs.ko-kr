---
title: "ODBC 연결 | Microsoft Docs"
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
  - "ODBC 연결, 구성"
  - "ODBC, 연결"
ms.assetid: c9df2fa6-d9e2-4335-b885-724662968691
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ODBC 연결
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ODBC 연결은 시스템의 제어판에서 구성됩니다.  ODBC 드라이버가 설치된 모든 데이터 소스에 대해 ODBC 연결을 만들 수 있습니다.  Visual C\+\+ 6.0 이상에는 텍스트 파일, Access, FoxPro, Paradox, dBASE, Excel, SQL Server 및 Oracle용 드라이버가 제공됩니다.  ODBC 연결을 만들면 자동으로 데이터 소스 이름\(DSN\)을 받습니다.  DSN은 나중에 ADO 데이터 컨트롤 및 RDO RemoteData 컨트롤과 같은 데이터 컨트롤에서 연결을 식별하는 데 사용됩니다.  
  
 **OLE DB 연결** OLE DB 연결을 구성할 때는 추가 작업이 필요하지 않습니다.  예를 들어, ODBC 데이터 소스를 만들면 ODBC용 OLE DB 공급자가 자동으로 이를 감지합니다.  
  
### ODBC 데이터 소스를 구성하려면  
  
1.  **시작**, **설정**, **제어판**을 차례로 클릭합니다.  
  
2.  제어판에서 32비트 ODBC\(Windows 95 또는 98\)나 ODBC\(Windows NT 또는 2000\)를 선택합니다.  
  
3.  **사용자 DSN**이나 **시스템 DSN** 탭을 클릭합니다.  **사용자 DSN** 탭에서는 특정 사용자가 사용할 데이터 소스 이름을 만들고, **시스템 DSN** 탭에서는 모든 사용자가 사용할 수 있는 데이터 소스를 만들 수 있습니다.  
  
4.  **추가**를 클릭하여 로컬에 설치된 ODBC 드라이버 목록을 표시합니다.  
  
5.  ISAM\(Indexed Sequential Access Methods\) 형식에 해당하는 드라이버나 연결할 데이터베이스를 선택하고 **마침**을 클릭합니다.  
  
6.  드라이버에 관련된 지침을 따릅니다.  대화 상자를 닫으면 DSN을 사용할 수 있습니다.  
  
 일부 ODBC 드라이버 형식에 대한 DSN을 생성할 때는 실제 파일의 위치를 알고 있어야 합니다.  예를 들어, Access DSN을 만들 경우에는 .mdb 파일의 위치를 알아야 합니다.  올바른 사용자 이름과 암호도 있어야 합니다.  예를 들어, 대부분의 Access 시스템의 사용자 이름은 *admin*입니다.  
  
 [Oracle](../../data/ado-rdo/oracle-connections.md) DSN을 만들 때는 SQL\*Net 연결 문자열을 알고 있어야 합니다.  
  
## 참고 항목  
 [데이터베이스 연결 만들기](../../data/ado-rdo/creating-database-connections.md)