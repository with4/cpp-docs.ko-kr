---
title: "XML 데이터 액세스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CStreamRowset 클래스, XML 데이터 검색"
  - "CXMLAccessor 클래스, XML 데이터 검색"
  - "데이터[C++], XML 데이터 액세스"
  - "데이터 액세스[C++], XML 데이터"
  - "행 집합[C++], XML 데이터 검색"
  - "XML[C++], 데이터 액세스"
ms.assetid: 6b693d55-a554-4846-8118-e8773b79b572
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# XML 데이터 액세스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

데이터 소스에서 XML 데이터를 검색하는 두 개의 메서드가 있습니다. 하나는 [CStreamRowset](../../data/oledb/cstreamrowset-class.md)을 사용하며 다른 하나는 [CXMLAccessor](../../data/oledb/cxmlaccessor-class.md)를 사용합니다.  
  
|기능|CStreamRowset|CXMLAccessor|  
|--------|-------------------|------------------|  
|전송되는 데이터의 양|한 번에 모든 열과 행에서 데이터를 검색합니다.|한 번에 모든 열과 하나의 행에서 데이터를 검색합니다.  `MoveNext`같은 메서드를 사용하여 행을 탐색해야 합니다.|  
|문자열 형식 지정|SQL Server는 XML 문자열을 형식 지정하여 소비자에게 전송합니다.|원시 형식으로 된 행 집합 데이터를 검색\(공급자에게 이 데이터를 유니코드 문자열로 전송하도록 요청\)한 다음, XML 형식의 데이터가 들어 있는 문자열을 빌드합니다.|  
|형식 제어|일부 SQL Server 2000 특정 속성을 설정하여 XML 문자열이 형식 지정되는 방법을 어느 정도 제어할 수 있습니다.|생성된 XML 문자열의 형식을 제어할 수 없습니다.|  
  
 `CStreamRowset`을 사용하면 XML 형식의 데이터를 보다 효과적으로 검색할 수 있지만, `CStreamRowset`은 SQL Server 2000에서만 지원됩니다.  
  
## CStreamRowset을 사용하여 XML 데이터 검색  
 `CCommand` 또는 `CTable` 선언에서 [CStreamRowset](../../data/oledb/cstreamrowset-class.md)을 행 집합 형식으로 지정하십시오.  CStreamRowset은 다음과 같이 사용자 고유의 접근자와 함께 사용되거나 접근자 없이 사용될 수도 있습니다.  
  
```  
CCommand<CAccessor<CMyAccessor>, CStreamRowset> myCmd;  
```  
  
 또는  
  
```  
CCommand<CNoAccessor, CStreamRowset> myCmd;  
```  
  
 일반적으로 `CRowset`을 `TRowset` 클래스로 지정하는 경우처럼 `CCommand::Open`을 호출하면 `IRowset` 포인터를 얻습니다.  `ICommand::Execute`는 `CRowset` 개체의 `m_spRowset` 멤버에 저장된 `IRowset` 포인터를 반환합니다.  `MoveFirst`, `MoveNext` 및 `GetData`와 같은 메서드는 이 포인터를 사용하여 데이터를 검색합니다.  
  
 이와 반대로, `CStreamRowset`을 `TRowset` 클래스로 지정하고 `CCommand::Open`을 호출하면, `ICommand::Execute`는 [CStreamRowset](../../data/oledb/cstreamrowset-class.md)의 `m_spStream` 데이터 멤버에 저장된 `ISequentialStream` 포인터를 반환합니다.  그런 다음 `Read` 메서드를 사용하여 XML 형식의 데이터\(유니코드 문자열\)를 검색합니다.  예를 들면 다음과 같습니다.  
  
```  
myCmd.m_spStream->Read()  
```  
  
 SQL Server 2000은 XML 형식 지정을 수행하고 행 집합의 모든 열과 행을 하나의 XML 문자열로 반환합니다.  
  
 `Read` 메서드 사용 예제는 [단순 소비자 구현](../../data/oledb/implementing-a-simple-consumer.md)의 "XML 지원을 소비자에 추가"를 참조하십시오.  
  
> [!NOTE]
>  `CStreamRowset`을 사용하는 XML 지원은 SQL Server 2000에서만 작동되며 MDAC와 함께 설치된 SQL Server 2000용 OLE DB 공급자가 있어야 합니다.  
  
## CXMLAccessor를 사용하여 XML 데이터 검색  
 [CXMLAccessor](../../data/oledb/cxmlaccessor-class.md)를 사용하면 데이터 저장소의 스키마에 대한 아무런 정보가 없을 때 데이터 소스의 데이터에 문자열 데이터로 액세스할 수 있습니다.  `CXMLAccessor`는 데이터 저장소에서 액세스한 모든 데이터를 태그가 지정된 XML 형식의 데이터로 변환한다는 점을 제외하고는 `CDynamicStringAccessorW`와 동일한 기능을 수행합니다.  XML 태그 이름은 데이터 저장소의 열 이름과 가능하면 거의 일치해야 합니다.  
  
 `CXMLAccessor`를 다른 접근자 클래스처럼 사용하여 `CCommand` 또는 `CTable`에 템플릿 매개 변수로 전달하십시오.  
  
```  
CTable<CXMLAccessor, CRowset> rs;  
```  
  
 [GetXMLRowData](../../data/oledb/cxmlaccessor-getxmlrowdata.md)를 사용하여 테이블 데이터를 한 번에 한 행씩 검색하고, `MoveNext` 같은 메서드를 사용하여 행을 탐색하십시오. 예를 들면 다음과 같습니다.  
  
```  
// Open data source, session, and rowset  
hr = rs.MoveFirst();  
while( SUCCEEDED(hr) && hr != DB_S_ENDOFROWSET )  
{  
    CStringW strRowData;  
    myCmd.GetXMLRowData(strRowData);  
  
    printf_s( "%S\n", strRowData );  
  
    hr = rs.MoveNext();  
}  
```  
  
 [GetXMLColumnData](../../data/oledb/cxmlaccessor-getxmlcolumndata.md)를 사용하여 해당 열\(데이터 형식\) 정보를 XML 형식 문자열 데이터로 검색할 수 있습니다.  
  
## 참고 항목  
 [접근자 사용](../../data/oledb/using-accessors.md)