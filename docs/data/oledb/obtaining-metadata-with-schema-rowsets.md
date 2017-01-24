---
title: "스키마 행 집합을 사용하여 메타데이터 구하기 | Microsoft Docs"
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
  - "메타데이터, 가져오기(OLE DB 템플릿)"
  - "OLE DB 소비자 템플릿, 공급자 메타데이터 얻기"
  - "스키마 행 집합, OLE DB 공급자 메타데이터 얻기"
ms.assetid: 6b448461-82fb-4acf-816b-3cbb0ca1d186
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 스키마 행 집합을 사용하여 메타데이터 구하기
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

행 집합을 열지 않고 공급자, 행 집합, 테이블, 열에 대한 정보나 다른 데이터베이스 정보를 구해야 하는 경우가 있습니다.  데이터베이스 구조에 대한 데이터는 메타데이터라고 하며 다양한 방법으로 검색할 수 있습니다.  한 가지 방법은 스키마 행 집합을 사용하는 것입니다.  
  
 OLE DB 템플릿은 스키마 정보를 검색하기 위한 일련의 클래스를 제공합니다. 이 클래스는 미리 정의된 스키마 행 집합을 생성하며 [스키마 행 집합 클래스 및 Typedef 클래스](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)에 나열됩니다.  
  
> [!NOTE]
>  OLAP를 사용 중이며 일부 행 집합이 스키마 행 집합 클래스에서 지원되지 않는 경우\(예: 다양한 수의 열이 있는 경우\) `CManualAccessor` 또는 `CDynamicAccessor`를 사용하는 것이 좋습니다.  열을 스크롤하고 case 문을 사용하여 각 열에 대한 가능한 데이터 형식을 처리할 수 있습니다.  
  
## 카탈로그\/스키마 모델  
 ANSI SQL은 데이터 저장소에 대한 카탈로그\/스키마 모델을 정의합니다. OLE DB는 이 모델을 사용합니다.  이 모델에서는 카탈로그\(데이터베이스\)에 스키마가 들어 있고, 스키마에 테이블이 들어 있습니다.  
  
-   **카탈로그** 카탈로그는 데이터베이스의 또 다른 이름입니다.  관련된 스키마의 모음입니다.  주어진 데이터 원본에 속한 카탈로그\(데이터베이스\)를 나열하려면 [CCatalog](../../data/oledb/ccatalogs-ccataloginfo.md)를 사용하세요.  많은 데이터베이스에 카탈로그가 하나만 있기 때문에, 메타데이터를 간단히 스키마 정보라고 부르기도 합니다.  
  
-   **스키마** 스키마는 특정 사용자가 소유하고 있거나 생성한 데이터베이스 개체의 모음입니다.  주어진 사용자가 소유한 스키마를 나열하려면 [CSchemata](../../data/oledb/cschemata-cschematainfo.md)를 사용하세요.  
  
     Microsoft SQL Server 및 ODBC 2.x 측면에서 스키마는 소유자입니다\(예: dbo는 일반적인 스키마 이름임\).  SQL Server는 테이블 집합에 메타데이터를 저장합니다. 한 테이블에는 모든 테이블의 목록이 포함되고, 다른 테이블에는 모든 열의 목록이 포함됩니다.  Microsoft Access 데이터베이스에는 스키마에 해당하는 요소가 없습니다.  
  
-   **테이블** 테이블은 특정 순서대로 정렬된 열의 모음입니다.  주어진 카탈로그\(데이터베이스\)에 정의된 테이블 및 이 테이블에 대한 정보를 나열하려면 [CTables](../../data/oledb/ctables-ctableinfo.md)를 사용하세요.  
  
## 제한  
 스키마 정보를 쿼리할 때 제한을 사용하여 관심 있는 정보 유형을 지정할 수 있습니다.  제한을 쿼리의 필터나 한정자로 생각할 수 있습니다.  예를 들어 다음 쿼리에서  
  
```  
SELECT * FROM authors where l_name = 'pivo'  
```  
  
 `l_name`이 제한 사항입니다.  이 경우는 제한 사항이 하나뿐인 아주 간단한 예제입니다. 스키마 행 집합 클래스는 몇 가지 제한을 지원합니다.  
  
 [스키마 행 집합 클래스 및 typedef 클래스](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)는 다른 행 집합처럼 인스턴스화하고 열어 스키마 행 집합에 액세스할 수 있도록 모든 OLE DB 스키마 행 집합을 캡슐화합니다.  예를 들어 typedef 클래스 [CColumns](../../data/oledb/ccolumns-ccolumnsinfo.md)는 다음과 같이 정의됩니다.  
  
```  
CRestrictions<CAccessor<CColumnsInfo>  
```  
  
 [CRestrictions](../../data/oledb/crestrictions-class.md) 클래스는 제한을 지원합니다.  스키마 행 집합의 인스턴스를 만든 후에 [CRestrictions::Open](../../data/oledb/crestrictions-open.md)을 호출합니다.  이 메서드는 지정하는 제한을 기반으로 결과 집합을 반환합니다.  
  
 제한을 지정하려면 [부록 B: 스키마 행 집합](http://go.microsoft.com/fwlink/?LinkId=64681)을 참조하고 사용 중인 행 집합을 조회하세요.  예를 들어 **CColumns**는 [COLUMNS 행 집합](http://go.microsoft.com/fwlink/?LinkId=64682)에 해당합니다. 항목에서는 COLUMNS 행 집합에서 제한 열이 나열됩니다\(TABLE\_CATALOG, TABLE\_SCHEMA, TABLE\_NAME, COLUMN\_NAME\).  제한을 지정할 때 이 순서를 따라야 합니다.  
  
 예를 들어 테이블 이름으로 제한하려는 경우 TABLE\_NAME이 세 번째 제한 열이라는 것을 확인하고 **열기**를 호출하여 다음 예제와 같이 원하는 테이블 이름을 세 번째 제한 매개 변수로 지정합니다.  
  
#### 스키마 행 집합을 사용하려면  
  
1.  헤더 파일 Atldbsch.h를 포함해야 합니다\(물론 소비자 지원을 위해 Atldbcli.h도 필요함\).  
  
2.  소비자의 헤더 파일이나 문서의 헤더 파일에서 스키마 행 집합 개체를 인스턴스화합니다.  테이블 정보를 원하는 경우 **CTables** 개체를 선언하고, 열 정보를 원하는 경우 **CColumns** 개체를 선언합니다.  이 예제에서는 authors 테이블의 열을 검색하는 방법을 보여 줍니다.  
  
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
  
3.  정보를 가져오려면 스키마 행 집합 개체의 적절한 데이터 멤버에 액세스합니다\(예: `ColumnSchemaRowset.m_szColumnName`\).  이는 COLUMN\_NAME에 해당합니다.  각 데이터 멤버에 해당하는 OLE DB 열을 보려면 [CColumns](../../data/oledb/ccolumns-ccolumnsinfo.md)를 참조하세요.  
  
 스키마 행 집합에 대한 참조를 위해 OLE DB 템플릿에서 typedef 클래스가 제공됩니다\([스키마 행 집합 클래스 및 Typedef 클래스](../../data/oledb/schema-rowset-classes-and-typedef-classes.md) 참조\).  
  
 제한 열을 포함하여 OLE DB 스키마 행 집합에 대한 자세한 내용은 OLE DB 프로그래머 참조의 [부록 B: 스키마 행 집합](http://go.microsoft.com/fwlink/?LinkId=64681)을 참조하세요.  
  
 스키마 행 집합 클래스를 사용하는 방법을 보여 주는 더 복잡한 예제는 [CatDB](http://msdn.microsoft.com/ko-kr/003d516b-2bf6-444e-8be5-4ebaa0b66046) 및 [DBViewer](http://msdn.microsoft.com/ko-kr/07620f99-c347-4d09-9ebc-2459e8049832) 샘플을 참조하세요.  
  
 스키마 행 집합과 관련한 공급자 지원에 대한 자세한 내용은 [스키마 행 집합 지원](../../data/oledb/supporting-schema-rowsets.md)을 참조하세요.  
  
## 참고 항목  
 [접근자 사용](../../data/oledb/using-accessors.md)