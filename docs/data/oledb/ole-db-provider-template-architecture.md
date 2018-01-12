---
title: "OLE DB 공급자 템플릿 구조 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- OLE DB [C++], object model
- architecture [C++], OLE DB Provider
- OLE DB provider templates, object model
ms.assetid: 639304a3-f9e0-44dc-8d0c-0ebd2455b363
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 8c1baa921f4a12aae40a01995cfd0b638cf614d8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="ole-db-provider-template-architecture"></a>OLE DB 공급자 템플릿 구조
## <a name="data-sources-and-sessions"></a>데이터 소스 및 세션  
 OLE DB 공급자 아키텍처에는 데이터 원본 개체를 하나 이상의 세션 포함 되어 있습니다. 데이터 원본 개체에는 모든 공급자를 인스턴스화해야 하는 초기 개체가입니다. 소비자 응용 프로그램 데이터를 요구 하는 경우 배치 공급자를 시작 하려면 데이터 원본 개체를 만듭니다. 데이터 원본 개체는 세션 개체를 만듭니다 (사용 하는 **IDBCreateSession** 인터페이스)를 통해 데이터 원본 개체에 연결 하는 소비자입니다. ODBC 프로그래머는 데이터 원본 개체를 생각할 수는 **HENV** 와 동등 하 게 세션 개체는 **HDBC**합니다.  
  
 ![공급자 아키텍처](../../data/oledb/media/vc4twb1.gif "vc4twb1")  
  
 OLE DB 공급자 마법사에서 생성 된 소스 파일을 함께 OLE DB 템플릿 데이터 원본 개체를 구현 합니다. 세션은 OLE DB에 해당 하는 개체 **TSession**합니다.  
  
## <a name="mandatory-and-optional-interfaces"></a>필수 및 선택적 인터페이스  
 OLE DB 공급자 템플릿 필요한 모든 인터페이스에 대 한 미리 패키지 된 구현을 제공합니다. 필수 및 선택적 인터페이스 개체의 여러 유형에 대 한 OLE DB에서 정의 됩니다.  
  
-   [데이터 원본](../../data/oledb/data-source-object-interfaces.md)  
  
-   [세션](../../data/oledb/session-object-interfaces.md)  
  
-   [행 집합](../../data/oledb/rowset-object-interfaces.md)  
  
-   [명령](../../data/oledb/command-object-interfaces.md)  
  
-   [트랜잭션](../../data/oledb/transaction-object-interfaces.md)  
  
 참고가 OLE DB 공급자 템플릿 행 및 저장소 개체를 구현 하지 않습니다.  
  
 다음 표에서 위에 나열 된 개체에 대 한 필수 및 선택적 인터페이스에 따라는 [OLE DB 2.6 SDK 설명서](https://msdn.microsoft.com/en-us/library/ms722784.aspx)합니다.  
  
|구성 요소|인터페이스|주석|  
|---------------|---------------|-------------|  
|[데이터 원본](../../data/oledb/data-source-object-interfaces.md) ([CDataSource](../../data/oledb/cdatasource-class.md))|[필수] **IDBCreateSession**<br /><br /> [필수] **IDBInitialize**<br /><br /> [필수]`IDBProperties`<br /><br /> [필수]`IPersist`<br /><br /> [선택 사항] **IConnectionPointContainer**<br /><br /> [선택 사항] **IDBAsynchStatus**<br /><br /> [선택 사항] **IDBDataSourceAdmin**<br /><br /> [선택 사항] **IDBInfo**<br /><br /> [선택 사항]`IPersistFile`<br /><br /> [선택 사항] **ISupportErrorInfo**|소비자에서 공급자에 연결 합니다. 개체 속성을 지정 하려면 사용자 ID, 암호 및 데이터 소스 이름과 같은 연결에서 사용 됩니다. 개체는 데이터 원본 관리를 사용할 수도 있습니다 (만들기, 업데이트, 삭제, 테이블, 및 등).|  
|[세션](../../data/oledb/session-object-interfaces.md) ([CSession](../../data/oledb/cdataconnection-operator-csession-amp.md))|[필수] **IGetDataSource**<br /><br /> [필수]`IOpenRowset`<br /><br /> [필수] **ISessionProperties**<br /><br /> [선택 사항] **IAlterIndex**<br /><br /> [선택 사항] **IAlterTable**<br /><br /> [선택 사항] **IBindResource**<br /><br /> [선택 사항] **ICreateRow**<br /><br /> [선택 사항] **IDBCreateCommand**<br /><br /> [선택 사항] **IDBSchemaRowset**<br /><br /> [선택 사항] **IIndexDefinition**<br /><br /> [선택 사항] **ISupportErrorInfo**<br /><br /> [선택 사항] **ITableCreation**<br /><br /> [선택 사항] **ITableDefinition**<br /><br /> [선택 사항] **ITableDefinitionWithConstraints**<br /><br /> [선택 사항] **ITransaction**<br /><br /> [선택 사항] **ITransactionJoin**<br /><br /> [선택 사항] **ITransactionLocal**<br /><br /> [선택 사항] **ITransactionObject**|세션 개체는 소비자와 공급자 간의 단일 대화를 나타냅니다. ODBC 다소 비슷하지만 **HSTMT** 있다는 여러 개의 세션이 활성화 될 수 있다는 점에서 합니다.<br /><br /> 세션 개체는 OLE DB 기능에 액세스할 기본 연결 합니다. 명령, 트랜잭션 또는 행 집합 개체를 가져오려면 세션 개체를 통해 이동 합니다.|  
|[행 집합](../../data/oledb/rowset-object-interfaces.md) ([CRowset](../../data/oledb/crowset-class.md))|[필수]`IAccessor`<br /><br /> [필수]`IColumnsInfo`<br /><br /> [필수] **IConvertType**<br /><br /> [필수]`IRowset`<br /><br /> [필수]`IRowsetInfo`<br /><br /> [선택 사항] **IChapteredRowset**<br /><br /> [선택 사항] **IColumnsInfo2**<br /><br /> [선택 사항] **IColumnsRowset**<br /><br /> [선택 사항] **IConnectionPointContainer**<br /><br /> [선택 사항] **IDBAsynchStatus**<br /><br /> [선택 사항] **IGetRow**<br /><br /> [선택 사항]`IRowsetChange`<br /><br /> [선택 사항] **IRowsetChapterMember**<br /><br /> [선택 사항] **IRowsetCurrentIndex**<br /><br /> [선택 사항] **IRowsetFind**<br /><br /> [선택 사항] **IRowsetIdentity**<br /><br /> [선택 사항] **IRowsetIndex**<br /><br /> [선택 사항]`IRowsetLocate`<br /><br /> [선택 사항] **IRowsetRefresh**<br /><br /> [선택 사항]`IRowsetScroll`<br /><br /> [선택 사항]`IRowsetUpdate`<br /><br /> [선택 사항] **IRowsetView**<br /><br /> [선택 사항] **ISupportErrorInfo**<br /><br /> [선택 사항] **IRowsetBookmark**|행 집합 개체는 데이터 원본에서 데이터를 나타냅니다. 이 개체는 데이터 소스의 해당 데이터 및 데이터에 대해 기본 작업 (업데이트, fetch, 이동, 등)에 대 한 바인딩해야 합니다. 항상 행 집합 개체를 포함 하 고 데이터를 조작 해야 합니다.|  
|[명령](../../data/oledb/command-object-interfaces.md) ([CCommand](http://msdn.microsoft.com/en-us/52bef5da-c1a0-4223-b4e6-9e464b6db409))|[필수]`IAccessor`<br /><br /> [필수]`IColumnsInfo`<br /><br /> [필수]`ICommand`<br /><br /> [필수] **ICommandProperties**<br /><br /> [필수]`ICommandText`<br /><br /> [필수] **IConvertType**<br /><br /> [선택 사항] **IColumnsRowset**<br /><br /> [선택 사항] **ICommandPersist**<br /><br /> [선택 사항] **ICommandPrepare**<br /><br /> [선택 사항]`ICommandWithParameters`<br /><br /> [선택 사항] **ISupportErrorInfo**<br /><br /> [선택 사항] **ICommandStream**|명령 개체는 쿼리 등 데이터에 대 한 작업을 처리합니다. 또는 매개 변수가 없는 매개 변수가 있는 문을 처리할 수 있습니다.<br /><br /> 또한 명령 개체는 매개 변수 및 출력 열에 대 한 바인딩을 처리 합니다. 한 바인딩은 행 집합에서의 열을 검색 해야 하는 방법에 대 한 정보를 포함 하는 구조입니다. 서 수, 데이터 형식, 길이 및 상태 등의 정보가 포함 됩니다.|  
|[트랜잭션](../../data/oledb/transaction-object-interfaces.md) (선택 사항)|[필수] **IConnectionPointContainer**<br /><br /> [필수] **ITransaction**<br /><br /> [선택 사항] **ISupportErrorInfo**|데이터 원본에 대해 작업의 원자 단위를 정의 하 고 이러한 작업 단위가 간의 관련 방식을 결정 하는 트랜잭션 개체입니다. 이 개체는 OLE DB 공급자 템플릿에서 직접 지원 되지 않습니다 (즉, 개체를 직접 만든).|  
  
 자세한 내용은 다음 항목을 참조하세요.  
  
-   [속성 맵](../../data/oledb/property-maps.md)  
  
-   [사용자 레코드](../../data/oledb/user-record.md)  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB 인터페이스](https://msdn.microsoft.com/en-us/library/ms709709.aspx)