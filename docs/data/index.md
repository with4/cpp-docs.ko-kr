---
layout: LandingPage
title: "Visual C++의 데이터 액세스"
translationtype: Human Translation
ms.sourcegitcommit: f9e63f47a8df69b52a6a12688e84602981d20dae
ms.openlocfilehash: 807cf772d632f66f74a210985ff611fc31ee594a
ms.lasthandoff: 03/21/2017

---
# <a name="data-access-in-visual-c"></a>Visual C++의 데이터 액세스

SQL과 NoSQL의 거의 모든 데이터베이스 제품에서는 네이티브 C++ 응용 프로그램에 대한 인터페이스를 제공합니다. 업계 표준 인터페이스는 모든 주요 SQL 데이터베이스 제품과 여러 NoSQL 제품에서 지원되는 ODBC입니다. 타사 제품의 경우 자세한 내용은 공급 업체에 문의하세요. 사용 조건이 다양한 타사 라이브러리도 사용할 수 있습니다.

Microsoft는 2011년부터 온-프레미스와 클라우드 모두에서 Microsoft SQL Server 데이터베이스에 연결하는 네이티브 응용 프로그램에 대한 표준으로 ODBC를 제공해 왔습니다. 자세한 내용은 [데이터 액세스 프로그래밍\(MFC-ATL\)](data-access-programming-mfc-atl.md)을 참조하세요. C++/CLI 라이브러리는 네이티브 ODBC 드라이버 또는 ADO.NET을 사용할 수 있습니다. 자세한 내용은 [ADO.NET을 사용하여 데이터 액세스(C++/CLI)](/dotnet/data-access-using-adonet-cpp-cli.md) 및 [Visual Studio에서 데이터 액세스](https://docs.microsoft.com/visualstudio/data-tools/accessing-data-in-visual-studio)를 참조하세요.

<ul class="panelContent cardsF">
<li>
        <a href="/azure/sql-database/sql-database-develop-cplusplus-simple">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardImageOuter">
                        <div class="cardImage">
                            <img src="/azure/media/index/SQLDatabase.svg" alt="" />
                        </div>
                    </div>
                    <div class="cardText">
                        <h3>C 및 C++를 사용하여 SQL Database에 연결</h3>
                        <p>C 또는 C++ 응용 프로그램에서 Azure SQL Database에 연결</p>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
    <li>
        <a href="https://github.com/Azure/azure-storage-cpp">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardImageOuter">
                        <div class="cardImage">
                            <img src="/azure/media/index/Storage.svg" alt="" />
                        </div>
                    </div>
                    <div class="cardText">
                        <h3>C++용 Microsoft Azure Storage Client Library</h3>
                        <p>[Azure Storage](/azure/storage/storage-introduction)는 내구성, 가용성, 확장성을 활용하여 고객의 요구 사항을 충족하는 최신 응용 프로그램을 위한 클라우드 저장소 솔루션입니다. C++용 Microsoft Azure Storage Client Library를 사용하여 C++에서 Azure Storage에 연결하세요.</p>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
    <li>
        <a href="https://blogs.msdn.microsoft.com/sqlnativeclient/2016/08/01/announcing-the-odbc-driver-13-1-for-sql-server/">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardImageOuter">
                        <div class="cardImage">
                            <img src="/media/common/i_drivers.svg" alt="" />
                        </div>
                    </div>
                    <div class="cardText">
                        <h3>ODBC Driver 13.1 for SQL Server – Windows 출시</h3>
                        <p>최신 ODBC 드라이버는 Microsoft SQL Server 2016 C/C++용 Microsoft Azure SQL Database 기반 응용 프로그램에 대한 강력한 데이터 액세스를 제공합니다. Always Encrypted, Azure Active Directory 및 AlwaysOn 가용성 그룹을 비롯한 여러 기능을 지원합니다. MacOS 및 Linux에서도 사용할 수 있습니다.</p>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
    <li>
        <a href="https://msdn.microsoft.com/library/ms130892.aspx">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardImageOuter">
                        <div class="cardImage">
                            <img src="/media/common/i_api.svg" alt="" />
                        </div>
                    </div>
                    <div class="cardText">
                        <h3>SQL Server Native Client</h3>
                        <p>SQL Server Native Client는 OLE DB 및 ODBC 모두에 사용되는 독립 실행형 데이터 액세스 API(응용 프로그래밍 인터페이스)로, SQL Server 2005에서 SQL Server 2014까지 지원합니다. 새 응용 프로그램은 ODBC Driver 13.1 for SQL Server를 사용해야 합니다.</p>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
    <li>
        <a href="/cpp/data/data-access-programming-mfc-atl">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardImageOuter">
                        <div class="cardImage">
                            <img src="/media/common/i_api.svg" alt="" />
                        </div>
                    </div>
                    <div class="cardText">
                        <h3>데이터 액세스 프로그래밍</h3>
                        <p>Visual C++를 사용하는 레거시 데이터 액세스 프로그래밍에 대해 설명합니다. 이 프로그램에서는 기본적으로 ATL(액티브 템플릿 클래스 라이브러리) 또는 MFC(Microsoft Foundation Class) 라이브러리와 같은 클래스 라이브러리 중 하나를 사용하므로 데이터베이스 API를 간편하게 사용할 수 있습니다.</p>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
    <li>
        <a href="/cpp/data/odbc/open-database-connectivity-odbc">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardImageOuter">
                        <div class="cardImage">
                            <img src="/media/common/i_multi-connect.svg" alt="" />
                        </div>
                    </div>
                    <div class="cardText">
                        <h3>ODBC(Open Database Connectivity)</h3>
                        <p>MFC(Microsoft Foundation Classes) 라이브러리는 ODBC(Open Database Connectivity)를 사용하여 프로그래밍하는 데 필요한 클래스를 제공합니다.</p>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
    <li>
        <a href="/cpp/data/oledb/ole-db-programming">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardImageOuter">
                        <div class="cardImage">
                            <img src="/media/common/i_generic-database.svg" alt="" />
                        </div>
                    </div>
                    <div class="cardText">
                        <h3>OLE DB 프로그래밍</h3>
                        <p>OLE DB 데이터베이스 기술 및 OLE DB 템플릿 라이브러리에 대해 설명하는 개념 항목에 대한 링크를 제공합니다. (연결된 서버가 포함된 시나리오를 제외하고는 새 응용 프로그램에 OLE DB를 사용하지 않는 것이 좋습니다.)</p>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
    
</ul>

---

<h2>참조</h2>

<ul class="panelContent cardsW">
 <li>
        <a href="https://azure.microsoft.com/develop/cpp/">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardText">
                        <h3>Microsoft Azure C 및 C++ 개발자 센터</h3>
                        <p>향상된 유연성, 확장성 및 안정성을 제공하는 Azure에서는 원하는 도구를 사용하여 C++ 응용 프로그램을 쉽게 빌드할 수 있습니다.</p>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
    <li>
        <a href="https://docs.microsoft.com/azure/storage/storage-c-plus-plus-how-to-use-blobs">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardText">
                        <h3>C++에서 Blob Storage를 사용하는 방법</h3>
                        <p>Azure Blob Storage는 클라우드에서 구조화되지 않은 데이터를 개체/Blob으로 저장하는 서비스입니다. Blob Storage는 문서, 미디어 파일, 응용 프로그램 설치 관리자 등과 같은 모든 유형의 텍스트 또는 이진 데이터를 저장할 수 있습니다. Blob Storage를 개체 저장소라고도 합니다.</p>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
    <li>
        <a href="https://docs.microsoft.com/sql/odbc/reference/odbc-programmer-s-reference">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardText">
                        <h3>ODBC 프로그래머 참조</h3>
                        <p>ODBC 인터페이스는 C 프로그래밍 언어와 함께 사용하도록 설계되었습니다. ODBC 인터페이스는 SQL 문, ODBC 함수 호출 및 C 프로그래밍의 세 가지 영역에서 사용됩니다.</p>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
    <li>
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardText">
                        <h3><a href="https://www.microsoft.com/download/details.aspx?id=53339" title="Microsoft® ODBC Driver 13.1 for SQL Server® - Windows Download Page">ODBC Driver 13.1 for SQL Server</a></h3>
                        <p>Microsoft ODBC Driver 13.1 for SQL Server는 네이티브 코드 API를 사용하여 Microsoft SQL Server 2008, SQL Server 2008 R2, SQL Server 2012, SQL Server 2016, Analytics Platform System, Azure SQL Database 및 Azure SQL Data Warehouse에 연결하는 응용 프로그램에 대한 런타임 지원을 포함하는 단일 DLL(동적 연결 라이브러리)입니다. 여기에서 드라이버를 다운로드하세요.</p>
                    </div>
                </div>
            </div>
        </div>        
    </li>
    
</ul>
