---
title: ODBC 및 MFC | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ODBC [C++], MFC
- connections [C++], databases
- connections [C++], data source
- databases [C++], connecting to
- data sources [C++], connecting to
- MFC [C++], ODBC and
- database connections [C++], MFC ODBC classes
ms.assetid: 98f02fd7-1235-437b-89a9-edfd0fc797f7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f9ab063bb44d9390442cbf5ad23a60f44f60b3c6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="odbc-and-mfc"></a>ODBC 및 MFC
> [!NOTE]
>  MFC 데이터베이스 클래스를 사용 하려면 데이터 원본에 대 한 적절 한 ODBC 드라이버가 필요 합니다. 최신 Microsoft ODBC driver for SQL Server는 [Microsoft ODBC Driver 13 for SQL Server](https://www.microsoft.com/en-us/download/details.aspx?id=50420)합니다. 대부분의 데이터베이스 공급 업체는 Windows 용 ODBC 드라이버를 제공합니다. 
  
 이 항목 Microsoft Foundation 클래스 (MFC) 라이브러리의 ODBC 기반 데이터베이스 클래스의 주요 개념을 소개 하 고 클래스 함께 작동 하는 방법의 개요를 제공 합니다. ODBC 및 MFC에 대 한 자세한 내용은 다음 항목을 참조 합니다.  
  
-   [데이터 소스에 연결](connecting-to-a-data-source.md)  
  
-   [레코드 선택 및 조작](selecting-and-manipulating-records.md)  
  
-   [폼에서 데이터의 표시와 조작](displaying-and-manipulating-data-in-a-form.md)  
  
-   [문서 및 뷰 작업](working-with-documents-and-views.md)  
  
-   [ODBC 및 SQL 액세스](access-to-odbc-and-sql.md)  
  
-   [MFC ODBC 클래스에 대한 추가 정보](further-reading-about-the-mfc-odbc-classes.md)  
  
 ODBC를 기반으로 하는 MFC 데이터베이스 클래스는 ODBC 드라이버를 사용할 수 있는 모든 데이터베이스에 대 한 액세스를 제공 하도록 설계 되었습니다. 클래스가 ODBC를 사용 하는 경우 응용 프로그램 데이터를 여러 다른 데이터 형식 및 다른 로컬/원격 구성에 액세스할 수 있습니다. 다른 데이터베이스 관리 시스템 (Dbms)를 처리 하는 특별 한 경우 코드를 작성할 필요가 없습니다. 액세스 하려는 데이터에 대 한 적절 한 ODBC 드라이버를 보유 하는 사용자가에 저장 된 테이블의 데이터를 조작 하기 위한 프로그램을 사용할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [ODBC(Open Database Connectivity)](open-database-connectivity-odbc.md)