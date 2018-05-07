---
title: OLE DB 소비자 템플릿 참조 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- vc-attr.db_param
- vc-attr.db_column
- vc-attr.db_accessor
- vc-attr.db_command
- vc-attr.db_table
- vc.templates.ole
- vc-attr.db_source
dev_langs:
- C++
helpviewer_keywords:
- OLE DB consumer templates, classes
ms.assetid: cfc7f698-1a0e-4a09-a4d3-ccb99e6654fe
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b5b599a1c7a1b256cc9c56d772a15621beda286f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="ole-db-consumer-templates-reference"></a>OLE DB 소비자 템플릿 참조
OLE DB 소비자 템플릿은 다음 클래스를 포함 합니다. 참조 자료도 포함 되어 항목에는 [OLE DB 소비자 템플릿에 대 한 매크로](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)합니다.  
  
## <a name="session-classes"></a>세션 클래스  
 [CDataConnection](../../data/oledb/cdataconnection-class.md)  
 데이터 소스와의 연결을 관리합니다. 필요한 개체 (데이터 소스 및 세션) 및 데이터 원본에 연결할 때 수행 해야 하는 작업의 일부를 캡슐화 하기 때문에 클라이언트를 만들기 위한 유용한 클래스입니다.  
  
 [CDataSource](../../data/oledb/cdatasource-class.md)  
 데이터 원본에 공급자를 통해 연결을 나타내는 OLE DB 데이터 원본 개체에 해당 합니다. 하나 이상의 데이터베이스 세션을 각로 표시 되는 `CSession` 개체, 단일 연결에서 수행할 수 있습니다.  
  
 [CEnumerator](../../data/oledb/cenumerator-class.md)  
 사용 가능한 데이터 원본에 대 한 행 집합 정보를 검색 하는 OLE DB 열거자 개체에 해당 합니다.  
  
 [CEnumeratorAccessor](../../data/oledb/cenumeratoraccessor-class.md)  
 사용 하는 `CEnumerator` 열거자 행 집합에서 데이터에 액세스할 수 있습니다. 이 행 집합의 데이터 소스와 현재 열거자에서 표시 하는 열거자 구성 됩니다.  
  
 [CSession](../../data/oledb/csession-class.md)  
 단일 데이터베이스 액세스 세션을 나타냅니다. 하나 이상의 세션에 각각 연결할 수 있습니다 `CDataSource` 개체입니다.  
  
## <a name="accessor-classes"></a>접근자 클래스  
 [CAccessor](../../data/oledb/caccessor-class.md)  
 데이터 원본에 정적으로 바인딩된 레코드에 사용 합니다. 데이터 원본의 구조를 알고 있는 경우이 접근자 클래스를 사용 합니다.  
  
 [CAccessorBase](../../data/oledb/caccessorbase-class.md)  
 모든 접근자 클래스에 대 한 기본 클래스입니다.  
  
 [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md)  
 만들 수 있는 런타임 시 행 집합의 열 정보를 기반으로 하는 접근자입니다. 이 클래스를 사용 하 여 데이터 원본의 구조 알 수 없는 경우 데이터를 검색 합니다.  
  
 [CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-class.md)  
 명령 유형을 알 수 없는 경우 사용할 수 있는 접근자입니다. 호출 하 여 매개 변수 정보를 가져옵니다는 `ICommandWithParameters` 인터페이스, 공급자 인터페이스를 지원 합니다.  
  
 [CDynamicStringAccessor](../../data/oledb/cdynamicstringaccessor-class.md)  
 데이터베이스의 기본 구조를 인식 하지 못합니다 때 데이터 원본에 액세스할 수 있습니다.  
  
 [CDynamicStringAccessorA](../../data/oledb/cdynamicstringaccessora-class.md)  
 유사한 `CDynamicStringAccessor` 제외 하 고이 클래스는 ANSI 문자열 데이터로 데이터 저장소에서 액세스 하는 데이터를 요청 합니다.  
  
 [CDynamicStringAccessorW](../../data/oledb/cdynamicstringaccessorw-class.md)  
 유사한 `CDynamicStringAccessor` 제외 하 고이 클래스는 유니코드 문자열 데이터와 데이터 저장소에서 액세스 하는 데이터를 요청 합니다.  
  
 [CManualAccessor](../../data/oledb/cmanualaccessor-class.md)  
 열 및 명령 매개 변수를 모두 처리 하도록 메서드로 접근자입니다. 이 클래스와 공급자에서 형식을 변환할 수으로 모든 데이터 형식에 사용할 수 있습니다.  
  
 [CNoAccessor](../../data/oledb/cnoaccessor-class.md)  
 출력 열 또는 매개 변수를 지원 하도록 클래스 하지 않을 때 템플릿 인수로 사용할 수 있습니다.  
  
 [CXMLAccessor](../../data/oledb/cxmlaccessor-class.md)  
 유사한 `CDynamicStringAccessor` 제외 하 고이 클래스는 XML 형식의 (태그 있음) 데이터로 데이터 저장소에서 액세스 하는 모든 데이터를 변환 합니다.  
  
## <a name="rowset-classes"></a>행 집합 클래스  
 [CAccessorRowset](../../data/oledb/caccessorrowset-class.md)  
 행 집합 및 해당 관련된 접근자를 캡슐화합니다.  
  
 [CArrayRowset](../../data/oledb/carrayrowset-class.md)  
 배열 구문을 사용 하 여 행 집합의 요소에 액세스 하는 데 사용 합니다.  
  
 [CBulkRowset](../../data/oledb/cbulkrowset-class.md)  
 인출 및 한 번의 호출으로 여러 행 핸들을 검색 하 여 대량에서 행을 조작 하는 데 사용 합니다.  
  
 [CNoRowset](../../data/oledb/cnorowset-class.md)  
 명령 행 집합을 반환 하지 않는 경우 템플릿 인수로 사용할 수 있습니다.  
  
 [CRestrictions](../../data/oledb/crestrictions-class.md)  
 스키마 행 집합에 대 한 제한을 지정 하는 데 사용 합니다.  
  
 [CRowset](../../data/oledb/crowset-class.md)  
 조작 설정 하 고 행 집합 데이터를 검색 하는 데 사용 합니다.  
  
 [CStreamRowset](../../data/oledb/cstreamrowset-class.md)  
 반환은 `ISequentialStream` ; 다음 사용 하는 대신 행 집합 개체는 **읽기** XML 형식으로 데이터를에서 검색 하는 메서드입니다. (SQL Server 2000은 서식을,이 기능은 SQL Server 2000과만 작동)  
  
 [IRowsetNotifyImpl](../../data/oledb/irowsetnotifyimpl-class.md)  
 에 대 한 더미 구현을 제공 `IRowsetNotify`에 대 한 빈 함수로 `IRowsetNotify` 메서드 `OnFieldChange`, `OnRowChange`, 및 `OnRowsetChange`합니다.  
  
 [스키마 행 집합 클래스 및 Typedef 클래스](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)  
  
 OLE DB 템플릿 클래스는 OLE DB 스키마 행 집합에 해당 하는 집합을 제공 합니다.  
  
## <a name="command-classes"></a>명령 클래스  
 [CCommand](../../data/oledb/ccommand-class.md)  
 설정 및 매개 변수 기반 OLE DB 명령을 실행 하는 데 사용 합니다. 단순 행 집합을 단순히 열을 사용 하 여 `CTable` 대신 합니다.  
  
 [CMultipleResults](../../data/oledb/cmultipleresults-class.md)  
 에 대 한 템플릿 인수로 사용 된 `CCommand` 서식 파일을 여러 결과 집합을 처리 하는 명령을 선택 합니다.  
  
 [CNoAccessor](../../data/oledb/cnoaccessor-class.md)  
 같은 템플릿 클래스에 대 한 템플릿 인수로 사용 `CCommand` 및 `CTable`, 접근자 클래스 인수를 사용 하는 합니다. 사용 하 여 `CNoAccessor` 출력 열 또는 매개 변수를 지원 하도록 클래스 하지 않도록 합니다.  
  
 [CNoMultipleResults](../../data/oledb/cnomultipleresults-class.md)  
 에 대 한 템플릿 인수로 사용 된 `CCommand` 서식 파일을 단일 행 집합을 처리 하는 명령을 선택 합니다. `CNoMultipleResults` 템플릿 인수에 대 한 기본값이입니다.  
  
 [CNoRowset](../../data/oledb/cnorowset-class.md)  
 에 대 한 템플릿 인수로 사용 `CCommand` 또는 `CTable` 명령 또는 테이블 행 집합을 반환 하지 않는 경우.  
  
 [CTable](../../data/oledb/ctable-class.md)  
 매개 변수가 없는 단순 행 집합에 액세스 하는 데 사용 합니다.  
  
## <a name="property-classes"></a>속성 클래스  
 [CDBPropIDSet](../../data/oledb/cdbpropidset-class.md)  
 속성 Id는 소비자가 속성 정보 배열을 전달 하는 데 사용 합니다. 속성이 한 속성 집합에 속해야 합니다.  
  
 [CDBPropSet](../../data/oledb/cdbpropset-class.md)  
 공급자의 속성을 설정 하는 데 사용 합니다.  
  
## <a name="bookmark-class"></a>책갈피 클래스  
 [CBookmark](../../data/oledb/cbookmark-class.md)  
 행 집합의 데이터에 액세스 하기 위한 인덱스로 사용 합니다.  
  
## <a name="error-class"></a>Error 클래스  
 [CDBErrorInfo](../../data/oledb/cdberrorinfo-class.md)  
 OLE DB 오류 정보를 검색 하는 데 사용 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 공급자 템플릿 참조](../../data/oledb/ole-db-provider-templates-reference.md)   
 [OLE DB 템플릿](../../data/oledb/ole-db-templates.md)