---
title: "스키마 행 집합 메타 데이터를 가져오기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- schema rowsets, getting OLE DB provider metadata
- OLE DB consumer templates, getting provider metadata
- metadata, getting (OLE DB Templates)
ms.assetid: 6b448461-82fb-4acf-816b-3cbb0ca1d186
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 0035606b02a1281b09287f19ffe087c9e6b36f7f
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/03/2018
---
# <a name="obtaining-metadata-with-schema-rowsets"></a>스키마 행 집합을 사용하여 메타데이터 구하기
행 집합을 열지 않고 공급자, 행 집합, 테이블, 열에 대한 정보나 다른 데이터베이스 정보를 구해야 하는 경우가 있습니다. 데이터베이스 구조에 대한 데이터는 메타데이터라고 하며 다양한 방법으로 검색할 수 있습니다. 한 가지 방법은 스키마 행 집합을 사용하는 것입니다.  
  
 스키마 정보를 검색 하기 위해 클래스 집합을 제공 하는 OLE DB 템플릿 이러한 클래스 미리 정의 된 스키마 행 집합을 만들고에 나열 된 [스키마 행 집합 클래스 및 Typedef 클래스](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)합니다.  
  
> [!NOTE]
>  OLAP를 사용 중이며 일부 행 집합이 스키마 행 집합 클래스에서 지원되지 않는 경우(예: 다양한 수의 열이 있는 경우) `CManualAccessor` 또는 `CDynamicAccessor`를 사용하는 것이 좋습니다. 열을 스크롤하고 case 문을 사용하여 각 열에 대한 가능한 데이터 형식을 처리할 수 있습니다.  
  
## <a name="catalogschema-model"></a>카탈로그/스키마 모델  
 ANSI SQL은 데이터 저장소에 대한 카탈로그/스키마 모델을 정의합니다. OLE DB는 이 모델을 사용합니다. 이 모델에서는 카탈로그(데이터베이스)에 스키마가 들어 있고, 스키마에 테이블이 들어 있습니다.  
  
-   **카탈로그** 카탈로그는 데이터베이스에 대 한 다른 이름입니다. 관련된 스키마의 컬렉션입니다. 지정된 된 데이터 소스에 속한 카탈로그 (데이터베이스)를 나열 하려면 사용 하 여 [CCatalog](../../data/oledb/ccatalogs-ccataloginfo.md)합니다. 많은 데이터베이스에 카탈로그가 하나만 있기 때문에, 메타데이터를 간단히 스키마 정보라고 부르기도 합니다.  
  
-   **스키마** 스키마가 소유 하 고 있거나 특정 사용자가 만든 데이터베이스 개체의 컬렉션입니다. 지정된 된 사용자가 소유한 스키마를 나열 하려면 사용 하 여 [CSchemata](../../data/oledb/cschemata-cschematainfo.md)합니다.  
  
     Microsoft SQL Server 및 ODBC 2.x 측면에서 스키마는 소유자 (예를 들어 dbo는 일반적인 스키마 이름임). SQL Server 테이블 집합에서 메타 데이터를 저장 하는 또한: 한 테이블에 있는 모든 테이블의 목록을 포함 하 고 다른 테이블의 모든 열 목록을 포함 합니다. Microsoft Access 데이터베이스에는 스키마에 해당하는 요소가 없습니다.  
  
-   **테이블** 테이블은 특정 순서 대로 정렬 된 열의 컬렉션입니다. 사용 하 여 해당 테이블에 대 한 정보와 주어진된 카탈로그 (데이터베이스)에 정의 된 테이블을 나열 하려면 [CTables](../../data/oledb/ctables-ctableinfo.md)).  
  
## <a name="restrictions"></a>제한  
 스키마 정보를 쿼리할 때 제한을 사용하여 관심 있는 정보 유형을 지정할 수 있습니다. 제한을 쿼리의 필터나 한정자로 생각할 수 있습니다. 예를 들어 다음 쿼리에서  
  
```  
SELECT * FROM authors where l_name = 'pivo'  
```  
  
 `l_name`이 제한 사항입니다. 이 경우는 제한 사항이 하나뿐인 아주 간단한 예제입니다. 스키마 행 집합 클래스는 몇 가지 제한을 지원합니다.  
  
 [스키마 행 집합 typedef 클래스](../../data/oledb/schema-rowset-classes-and-typedef-classes.md) 여 인스턴스화하고 열어 스키마 행 집합을 다른 행 집합 처럼 액세스할 수 있도록 모든 OLE DB 스키마 행 집합을 캡슐화 합니다. 예를 들어 typedef 클래스 [CColumns](../../data/oledb/ccolumns-ccolumnsinfo.md) 로 정의 됩니다.  
  
```  
CRestrictions<CAccessor<CColumnsInfo>  
```  
  
 [CRestrictions](../../data/oledb/crestrictions-class.md) 제한을 지원 클래스를 제공 합니다. 스키마 행 집합의 인스턴스를 만든 후 호출 [crestrictions:: Open](../../data/oledb/crestrictions-open.md)합니다. 이 메서드는 지정하는 제한을 기반으로 결과 집합을 반환합니다.  
  
 제한 사항을 지정 하려면를 참조 [부록 b: 스키마 행 집합](http://go.microsoft.com/fwlink/p/?linkid=64681) 사용 하는 행 집합을 찾습니다. 예를 들어 **CColumns** 에 해당 하는 [COLUMNS 행 집합](http://go.microsoft.com/fwlink/p/?linkid=64682); 해당 항목에서는 COLUMNS 행 집합에서 제한 열 나열: TABLE_CATALOG, TABLE_SCHEMA, TABLE_NAME, COLUMN_NAME 합니다. 제한을 지정할 때 이 순서를 따라야 합니다.  
  
 따라서 예를 들어 테이블 이름으로 제한 하려는 경우 TABLE_NAME이 세 번째 열에는 한 다음 호출 **열려**, 다음 예제와 같이 원하는 테이블 이름을 세 번째 제한 매개 변수로 지정 합니다.  
  
#### <a name="to-use-schema-rowsets"></a>스키마 행 집합을 사용하려면  
  
1.  헤더 파일 Atldbsch.h를 포함해야 합니다(물론 소비자 지원을 위해 Atldbcli.h도 필요함).  
  
2.  소비자의 헤더 파일이나 문서의 헤더 파일에서 스키마 행 집합 개체를 인스턴스화합니다. 테이블 정보를 원하는 경우에 선언 된 **CTables** 개체; 열 정보를 원하는 경우에 선언는 **CColumns** 개체입니다. 이 예제에서는 authors 테이블의 열을 검색하는 방법을 보여 줍니다.  
  
    ```  
    CDataSource ds;  
    ds.Open();  
    CSession ss;  
    ss.Open();  
    CColumns ColumnSchemaRowset;  
    // TABLE_NAME is the third restriction column, so  
    // specify "authors" as the third restriction parameter:  
    hr = ColumnSchemaRowset.Open(ss, NULL, NULL, "authors");  
    hr = ColumnSchemaRowset.MoveFirst();  
    while (hr == S_OK)  
    {  
       hr = ColumnSchemaRowset.MoveNext();  
    }  
    ```  
  
3.  정보를 가져오려면 스키마 행 집합 개체의 적절한 데이터 멤버에 액세스합니다(예: `ColumnSchemaRowset.m_szColumnName`). 이는 COLUMN_NAME에 해당합니다. 각 데이터 멤버에 해당 하는 OLE DB 열을 보려면 참조 [CColumns](../../data/oledb/ccolumns-ccolumnsinfo.md)합니다.  
  
 스키마 행 집합의 참조를 위해 typedef 클래스가 제공 OLE DB 템플릿 (참조 [스키마 행 집합 클래스 및 Typedef 클래스](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)).  
  
 OLE DB 스키마 행 집합을 포함 하는 제한 열에 대 한 자세한 내용은 참조 하십시오. [부록 b: 스키마 행 집합](http://go.microsoft.com/fwlink/p/?linkid=64681) OLE DB 프로그래머 참조에서.  
  
 스키마 행 집합 클래스를 사용 하는 방법의 더 복잡 한 예제를 참조 하십시오.는 [CatDB](http://msdn.microsoft.com/en-us/003d516b-2bf6-444e-8be5-4ebaa0b66046) 및 [DBViewer](http://msdn.microsoft.com/en-us/07620f99-c347-4d09-9ebc-2459e8049832) 샘플입니다.  
  
 스키마 행 집합에 대 한 공급자 지원에 대 한 정보를 참조 하십시오. [스키마 행 집합 지원](../../data/oledb/supporting-schema-rowsets.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [접근자 사용](../../data/oledb/using-accessors.md)