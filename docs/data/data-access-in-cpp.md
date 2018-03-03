---
title: "Visual c + +에서 데이터 액세스 | Microsoft Docs"
ms.custom: 
ms.date: 03/28/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- Visual C++, data access applications
- databases [C++]
- OLE DB [C++], data access technologies
- data [C++], data access technologies
- data access [C++], class libraries for databases
ms.assetid: 95da6237-bbe2-480a-ae50-3a520051ceff
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: eaefb5f3ed8bd0c586e42527d47918dbb0dd5a57
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="data-access-in-visual-c"></a>Visual C++의 데이터 액세스

SQL과 NoSQL의 거의 모든 데이터베이스 제품에서는 네이티브 C++ 응용 프로그램에 대한 인터페이스를 제공합니다. 업계 표준 인터페이스는 모든 주요 SQL 데이터베이스 제품과 여러 NoSQL 제품에서 지원되는 ODBC입니다. 타사 제품의 경우 자세한 내용은 공급 업체에 문의하세요. 사용 조건이 다양한 타사 라이브러리도 사용할 수 있습니다.

Microsoft는 2011년부터 온-프레미스와 클라우드 모두에서 Microsoft SQL Server 데이터베이스에 연결하는 네이티브 응용 프로그램에 대한 표준으로 ODBC를 제공해 왔습니다. 자세한 내용은 [데이터 액세스 프로그래밍\(MFC-ATL\)](data-access-programming-mfc-atl.md)을 참조하세요. C++/CLI 라이브러리는 네이티브 ODBC 드라이버 또는 ADO.NET을 사용할 수 있습니다. 자세한 내용은 [ADO.NET을 사용하여 데이터 액세스(C++/CLI)](/dotnet/data-access-using-adonet-cpp-cli.md) 및 [Visual Studio에서 데이터 액세스](https://docs.microsoft.com/visualstudio/data-tools/accessing-data-in-visual-studio)를 참조하세요.

## <a name="in-this-section"></a>섹션 내용
[데이터 액세스 프로그래밍 (MFC/ATL)](data-access-programming-mfc-atl.md) 하는 방법을 설명 레거시 데이터 액세스 여기서는 기본 방법은 클래스 라이브러리 ATL (액티브 템플릿) 또는 Microsoft Foundation 클래스 (MFC) 라이브러리와 같은 클래스 라이브러리 중 하나를 사용 하는, Visual c + + 프로그래밍 데이터베이스 Api 작업을 간소화합니다.

[데이터베이스 연결 (ODBC)를 열고](odbc/open-database-connectivity-odbc.md) Microsoft Foundation 클래스 (MFC) 라이브러리와 연결 ODBC (Open Database) 프로그래밍에 대 한 클래스를 제공 합니다.

[OLE DB 프로그래밍](oledb/ole-db-programming.md) 연결 된 서버에 대해 프로그래밍 하는 경우에 특히 일부 시나리오에서 여전히 필요한 대부분의 레거시 인터페이스입니다.

## <a name="related-topics"></a>관련 항목
[C 및 c + +를 사용 하 여 SQL 데이터베이스에 연결](/azure/sql-database/sql-database-develop-cplusplus-simple) C 또는 c + + 응용 프로그램에서 Azure SQL 데이터베이스에 연결 합니다.

[C + + 용 Microsoft Azure 저장소 클라이언트 라이브러리](https://github.com/Azure/azure-storage-cpp)
[Azure 저장소](/azure/storage/storage-introduction) 내구성, 가용성 및 확장성 요구를 충족 하기 위해 사용 하는 최신 응용 프로그램에 대 한 클라우드 저장소 솔루션은 해당 고객 합니다. C++용 Microsoft Azure Storage Client Library를 사용하여 C++에서 Azure Storage에 연결하세요.

[ODBC Driver 13.1 for SQL Server-Windows 출시](https://blogs.msdn.microsoft.com/sqlnativeclient/2016/08/01/announcing-the-odbc-driver-13-1-for-sql-server) C/c + + 기반 응용 프로그램에 대 한 최신 ODBC 드라이버는 Microsoft SQL Server 2016 Microsoft Azure SQL 데이터베이스에 강력한 데이터 액세스를 제공 합니다. 항상 암호화 기능을 포함 하 여에 대 한 지원, Azure Active Directory 및 AlwaysOn 가용성 그룹을 제공 합니다. MacOS 및 Linux에서도 사용할 수 있습니다.     
 
[SQL Server Native Client](/sql/relational-databases/native-client/sql-server-native-client-programming) SQL Server Native Client는 독립 실행형 데이터 액세스 응용 프로그래밍 인터페이스 (API) OLE DB 및 ODBC를 지 원하는 SQL Server 2014를 통해 SQL Server 2005 모두에 사용 합니다. 새 응용 프로그램은 ODBC Driver 13.1 for SQL Server를 사용해야 합니다.

[Microsoft Azure C 및 c + + 개발자 센터](https://azure.microsoft.com/develop/cpp/) Azure를 사용 하면 쉽게 유연성이 향상된, 확장성 및 안정성을 선호 하십니까 도구를 사용 하 여 c + + 응용 프로그램을 빌드할 수 있습니다.    

[C + +에서 Blob 저장소를 사용 하는 방법](https://docs.microsoft.com/azure/storage/storage-c-plus-plus-how-to-use-blobs) Azure Blob 저장소는 클라우드에서 개체/blob으로 구조화 되지 않은 데이터를 저장 하는 서비스입니다. Blob Storage는 문서, 미디어 파일, 응용 프로그램 설치 관리자 등과 같은 모든 유형의 텍스트 또는 이진 데이터를 저장할 수 있습니다. Blob Storage를 개체 저장소라고도 합니다.

[ODBC 프로그래머 참조](https://docs.microsoft.com/sql/odbc/reference/odbc-programmer-s-reference) The ODBC 인터페이스는 C 프로그래밍 언어에 사용 하도록 설계 되었습니다. ODBC 인터페이스는 SQL 문, ODBC 함수 호출 및 C 프로그래밍의 세 가지 영역에서 사용됩니다.

## <a name="see-also"></a>참고 항목
[Visual C++](../visual-cpp-in-visual-studio.md)
