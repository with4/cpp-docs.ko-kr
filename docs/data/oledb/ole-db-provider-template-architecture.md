---
title: "OLE DB 공급자 템플릿 구조 | Microsoft Docs"
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
  - "아키텍처[C++], OLE DB 공급자"
  - "OLE DB[C++], 개체 모델"
  - "OLE DB 공급자 템플릿, 개체 모델"
ms.assetid: 639304a3-f9e0-44dc-8d0c-0ebd2455b363
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# OLE DB 공급자 템플릿 구조
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## 데이터 소스 및 세션  
 OLE DB 공급자 구조에는 데이터 소스 개체 하나와 세션이 하나 이상 포함됩니다.  데이터 소스 개체는 모든 공급자가 인스턴스화해야 하는 초기 개체입니다.  소비자 응용 프로그램에서는 데이터가 필요한 경우 공동으로 데이터 소스 개체를 만들어 공급자를 시작합니다.  데이터 소스 개체는 **IDBCreateSession** 인터페이스를 사용하여 세션 개체를 만들고, 소비자는 이 세션 개체를 통해 데이터 소스 개체에 연결합니다.  ODBC 프로그래머는 데이터 소스 개체를 **HENV**에 해당하는 요소로, 세션 개체는 **HDBC**에 해당하는 요소로 생각하면 됩니다.  
  
 ![공급자 아키텍처](../../data/oledb/media/vc4twb1.gif "vc4TWB1")  
  
 OLE DB 템플릿은 ATL OLE DB 공급자 마법사가 만든 소스 파일과 함께 데이터 소스 개체를 구현합니다.  세션은 OLE DB **TSession**에 해당하는 개체입니다.  
  
## 필수 인터페이스 및 선택적 인터페이스  
 OLE DB 공급자 템플릿은 모든 필수 인터페이스에 대해 미리 패키지된 구현을 제공합니다.  OLE DB는 필수 인터페이스 및 선택적 인터페이스를 다음과 같은 몇 가지 개체 유형으로 정의합니다.  
  
-   [데이터 소스](../../data/oledb/data-source-object-interfaces.md)  
  
-   [세션](../../data/oledb/session-object-interfaces.md)  
  
-   [행 집합](../../data/oledb/rowset-object-interfaces.md)  
  
-   [명령](../../data/oledb/command-object-interfaces.md)  
  
-   [트랜잭션](../../data/oledb/transaction-object-interfaces.md)  
  
 OLE DB 공급자 템플릿은 행 개체와 저장소 개체를 구현하지 않습니다.  
  
 다음 표에서는 [OLE DB 2.6 SDK Documentation](https://msdn.microsoft.com/en-us/library/ms722784.aspx)에 따라 위에 나열된 개체에 대한 필수 인터페이스와 선택적 인터페이스를 보여 줍니다.  
  
|구성 요소|인터페이스|주석|  
|-----------|-----------|--------|  
|[데이터 소스](../../data/oledb/data-source-object-interfaces.md)\([CDataSource](../../data/oledb/cdatasource-class.md)\)|\[mandatory\] **IDBCreateSession**<br /><br /> \[mandatory\] **IDBInitialize**<br /><br /> \[mandatory\] `IDBProperties`<br /><br /> \[mandatory\] `IPersist`<br /><br /> \[optional\] **IConnectionPointContainer**<br /><br /> \[optional\] **IDBAsynchStatus**<br /><br /> \[optional\] **IDBDataSourceAdmin**<br /><br /> \[optional\] **IDBInfo**<br /><br /> \[optional\] `IPersistFile`<br /><br /> \[optional\] **ISupportErrorInfo**|소비자에서 공급자로 연결.  이 개체는 사용자 ID, 암호 및 데이터 소스 이름과 같은 연결 속성을 지정하는 데 사용됩니다.  테이블을 만들거나, 업데이트하거나, 삭제하는 등 데이터 소스를 관리하는 데도 사용됩니다.|  
|[세션](../../data/oledb/session-object-interfaces.md)\([CSession](../../data/oledb/cdataconnection-operator-csession-amp.md)\)|\[mandatory\] **IGetDataSource**<br /><br /> \[mandatory\] `IOpenRowset`<br /><br /> \[mandatory\] **ISessionProperties**<br /><br /> \[optional\] **IAlterIndex**<br /><br /> \[optional\] **IAlterTable**<br /><br /> \[optional\] **IBindResource**<br /><br /> \[optional\] **ICreateRow**<br /><br /> \[optional\] **IDBCreateCommand**<br /><br /> \[optional\] **IDBSchemaRowset**<br /><br /> \[optional\] **IIndexDefinition**<br /><br /> \[optional\] **ISupportErrorInfo**<br /><br /> \[optional\] **ITableCreation**<br /><br /> \[optional\] **ITableDefinition**<br /><br /> \[optional\] **ITableDefinitionWithConstraints**<br /><br /> \[optional\] **ITransaction**<br /><br /> \[optional\] **ITransactionJoin**<br /><br /> \[optional\] **ITransactionLocal**<br /><br /> \[optional\] **ITransactionObject**|세션 개체는 소비자와 공급자 사이에 이루어진 한 번의 대화를 나타냅니다.  동시에 여러 개의 세션이 활성화될 수 있다는 점에서 ODBC **HSTMT**와 비슷합니다.<br /><br /> 세션 개체는 OLE DB 기능에 액세스하는 기본 연결입니다.  명령이나 트랜잭션 또는 행 집합 개체에 액세스하려면 세션 개체를 통과해야 합니다.|  
|[행 집합](../../data/oledb/rowset-object-interfaces.md)\([CRowset](../../data/oledb/crowset-class.md)\)|\[mandatory\] `IAccessor`<br /><br /> \[mandatory\] `IColumnsInfo`<br /><br /> \[mandatory\] **IConvertType**<br /><br /> \[mandatory\] `IRowset`<br /><br /> \[mandatory\] `IRowsetInfo`<br /><br /> \[optional\] **IChapteredRowset**<br /><br /> \[optional\] **IColumnsInfo2**<br /><br /> \[optional\] **IColumnsRowset**<br /><br /> \[optional\] **IConnectionPointContainer**<br /><br /> \[optional\] **IDBAsynchStatus**<br /><br /> \[optional\] **IGetRow**<br /><br /> \[optional\] `IRowsetChange`<br /><br /> \[optional\] **IRowsetChapterMember**<br /><br /> \[optional\] **IRowsetCurrentIndex**<br /><br /> \[optional\] **IRowsetFind**<br /><br /> \[optional\] **IRowsetIdentity**<br /><br /> \[optional\] **IRowsetIndex**<br /><br /> \[optional\] `IRowsetLocate`<br /><br /> \[optional\] **IRowsetRefresh**<br /><br /> \[optional\] `IRowsetScroll`<br /><br /> \[optional\] `IRowsetUpdate`<br /><br /> \[optional\] **IRowsetView**<br /><br /> \[optional\] **ISupportErrorInfo**<br /><br /> \[optional\] **IRowsetBookmark**|행 집합 개체는 데이터 소스의 데이터를 나타냅니다.  이 개체는 데이터 소스의 데이터 및 데이터에 대한 기본 작업\(업데이트, 페치, 이동 등\)을 바인딩해야 합니다.  데이터를 포함하고 조작하기 위한 행 집합 개체는 항상 있습니다.|  
|[명령](../../data/oledb/command-object-interfaces.md)\([CCommand](http://msdn.microsoft.com/ko-kr/52bef5da-c1a0-4223-b4e6-9e464b6db409)\)|\[mandatory\] `IAccessor`<br /><br /> \[mandatory\] `IColumnsInfo`<br /><br /> \[mandatory\] `ICommand`<br /><br /> \[mandatory\] **ICommandProperties**<br /><br /> \[mandatory\] `ICommandText`<br /><br /> \[mandatory\] **IConvertType**<br /><br /> \[optional\] **IColumnsRowset**<br /><br /> \[optional\] **ICommandPersist**<br /><br /> \[optional\] **ICommandPrepare**<br /><br /> \[optional\] `ICommandWithParameters`<br /><br /> \[optional\] **ISupportErrorInfo**<br /><br /> \[optional\] **ICommandStream**|명령 개체는 쿼리 등과 같이 데이터에 대한 작업을 처리합니다.  매개 변수가 있거나 매개 변수가 없는 명령문을 처리할 수 있습니다.<br /><br /> 또한 명령 개체는 매개 변수와 출력 열에 대한 바인딩 처리 작업을 담당합니다.  바인딩은 행 집합에서의 열 검색 방법에 대한 정보가 포함된 구조입니다.  서수, 데이터 형식, 길이, 상태 등의 정보가 포함됩니다.|  
|[트랜잭션](../../data/oledb/transaction-object-interfaces.md)\(선택적 요소\)|\[mandatory\] **IConnectionPointContainer**<br /><br /> \[mandatory\] **ITransaction**<br /><br /> \[optional\] **ISupportErrorInfo**|트랜잭션 개체는 데이터 소스에 대한 작업의 원자 단위를 정의하고 이러한 작업 단위가 서로 연관되는 방법을 결정합니다.  이 개체는 OLE DB 공급자 템플릿이 직접 지원하지 않으므로 사용자가 직접 만들어야 합니다.|  
  
 자세한 내용은 다음 항목을 참조하십시오.  
  
-   [속성 맵](../../data/oledb/property-maps.md)  
  
-   [사용자 레코드](../../data/oledb/user-record.md)  
  
## 참고 항목  
 [OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB Interfaces](https://msdn.microsoft.com/en-us/library/ms709709.aspx)