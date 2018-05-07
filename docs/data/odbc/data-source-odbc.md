---
title: 데이터 원본 (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ODBC data sources, configuring
- CDatabase class, data source connections
- ODBC data sources
- configuring ODBC data sources
- ODBC data sources, represented by CDatabase
ms.assetid: b246721f-b9e1-49bd-a6c7-f348b8c3d537
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 842a8bf3faadcf96b4f44441e45dc94d5679f9f4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="data-source-odbc"></a>데이터 소스(ODBC)
MFC ODBC 클래스에이 항목에 적용 됩니다.  
  
 데이터베이스의 경우 데이터 소스는 특정 집합의 데이터를 해당 데이터와 데이터 소스 이름을 사용 하 여 표시할 수 있는 데이터 원본의 위치에 액세스 하는 데 필요한 정보입니다. 클래스를 사용 하려면 [CDatabase](../../mfc/reference/cdatabase-class.md), 데이터 원본 연결 ODBC (Open Database) 관리자를 통해 구성 된 하나 여야 합니다. 데이터 원본의 예로 네트워크 또는 로컬 디렉터리에서 Microsoft Access 파일에서 Microsoft SQL Server에서 실행 되는 원격 데이터베이스입니다. 응용 프로그램에서 ODBC 드라이버는 권한이 있는 모든 데이터 원본에 액세스할 수 있습니다.  
  
 하나 이상의 데이터 소스를 한 번에 응용 프로그램에서 활성화 수, 각으로 표시 되는 `CDatabase` 개체입니다. 모든 데이터 소스에 여러 개의 동시 연결을 수도 수 있습니다. 원격으로 설치한 드라이버 및 ODBC 드라이버의 기능에 따라 로컬 데이터 소스에 연결할 수 있습니다. 데이터 원본 및 ODBC 관리자에 대 한 자세한 내용은 참조 [ODBC](../../data/odbc/odbc-basics.md) 및 [ODBC 관리자](../../data/odbc/odbc-administrator.md)합니다.  
  
 다음 항목에서는 데이터 원본에 대 한 추가:  
  
-   [데이터 소스: 연결 관리(ODBC)](../../data/odbc/data-source-managing-connections-odbc.md)  
  
-   [데이터 소스: 데이터 소스의 스키마 확인(ODBC)](../../data/odbc/data-source-determining-the-schema-of-the-data-source-odbc.md)  
  
## <a name="see-also"></a>참고 항목  
 [ODBC(Open Database Connectivity)](../../data/odbc/open-database-connectivity-odbc.md)