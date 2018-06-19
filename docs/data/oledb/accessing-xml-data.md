---
title: XML 데이터 액세스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- data access [C++], XML data
- XML [C++], accessing data
- CXMLAccessor class, retrieving XML data
- data [C++], XML data access
- rowsets [C++], retrieving XML data
- CStreamRowset class, retrieving XML data
ms.assetid: 6b693d55-a554-4846-8118-e8773b79b572
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f3abe00adee2a88d0414d688984232422a5bcfc0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33093404"
---
# <a name="accessing-xml-data"></a>XML 데이터 액세스
데이터 소스에서 XML 데이터를 검색 하는 두 개의 메서드가: 하나 사용 하 여 [CStreamRowset](../../data/oledb/cstreamrowset-class.md) 다른 사용 [CXMLAccessor](../../data/oledb/cxmlaccessor-class.md)합니다.  
  
|기능|CStreamRowset|CXMLAccessor|  
|-------------------|-------------------|------------------|  
|전송 데이터의 양|한 번에 모든 열과 행에서 데이터를 검색합니다.|모든 열에서 데이터를 검색 하지만 한 번에 한 행만 있습니다. 와 같은 메서드를 사용 하 여 행을 탐색 해야 `MoveNext`합니다.|  
|문자열의 서식을 지정|SQL Server는 XML 문자열의 형식을 지정 하 고 소비자에 게 보냅니다.|행 집합 데이터의 네이티브 형식 (공급자 유니코드 문자열로 전송 요청)을 검색 하 고 그런 다음 XML 형식으로 데이터를에서 포함 하는 문자열을 작성 합니다.|  
|형식 제어|일부 SQL Server 2000 관련 속성을 설정 하 여 XML 문자열 형식 지정 방법을 제어할 일정 수준의 해야 합니다.|해야 생성 된 XML 문자열의 서식 제어할 수 없습니다.|  
  
 반면 `CStreamRowset` 제공 XML 형식으로 데이터를 검색 하는 보다 효과적으로 SQL Server 2000 에서만 지원 됩니다.  
  
## <a name="retrieving-xml-data-using-cstreamrowset"></a>CStreamRowset를 사용 하 여 XML 데이터 검색  
 지정한 [CStreamRowset](../../data/oledb/cstreamrowset-class.md) 에서 행 집합 형식으로 프로그램 `CCommand` 또는 `CTable` 선언 합니다. 사용할 수 있습니다 사용자 고유의 접근자 또는 접근자가 없습니다 예:  
  
```  
CCommand<CAccessor<CMyAccessor>, CStreamRowset> myCmd;  
```  
  
 -또는-  
  
```  
CCommand<CNoAccessor, CStreamRowset> myCmd;  
```  
  
 일반적으로 호출 하는 경우 `CCommand::Open` (예를 들어 지정 하 `CRowset` 으로 `TRowset` 클래스)을 가져와서는 `IRowset` 포인터. `ICommand::Execute` 반환는 `IRowset` 에 저장 된 포인터는 `m_spRowset` 의 멤버는 `CRowset` 개체입니다. 와 같은 메서드 `MoveFirst`, `MoveNext`, 및 `GetData` 해당 포인터를 사용 하 여 데이터를 검색 합니다.  
  
 이와 반대로 호출 하는 경우 `CCommand::Open` (하지만 지정 `CStreamRowset` 로 `TRowset` 클래스), `ICommand::Execute` 반환는 `ISequentialStream` 에 저장 된 포인터는 `m_spStream` 데이터 멤버의 [CStreamRowset](../../data/oledb/cstreamrowset-class.md). 사용 하 여는 `Read` 메서드를 XML 형식 (유니코드 문자열) 데이터를 검색 합니다. 예를 들어:  
  
```  
myCmd.m_spStream->Read()  
```  
  
 SQL Server 2000에서 XML 서식 지정을 수행 하 고 모든 열과 하나의 XML 문자열로 행 집합의 모든 행을 반환 합니다.  
  
 사용 하는 예제는 `Read` 메서드를 "XML 지원 소비자에 추가"의 참조 [단순 소비자 구현](../../data/oledb/implementing-a-simple-consumer.md)합니다.  
  
> [!NOTE]
>  XML을 사용 하 여 지원 `CStreamRowset` SQL Server 2000 에서만 작동 하 고 SQL Server 2000 (mdac를 사용할 경우 설치 됨)에 대 한 OLE DB Provider가 있어야 합니다.  
  
## <a name="retrieving-xml-data-using-cxmlaccessor"></a>CXMLAccessor를 사용 하 여 XML 데이터 검색  
 [CXMLAccessor](../../data/oledb/cxmlaccessor-class.md) 데이터 저장소의 스키마 모를 때 데이터 원본에서 문자열 데이터로 액세스할 수 있습니다. `CXMLAccessor` 처럼 작동 `CDynamicStringAccessorW` 제외 하 고 전자 (태그 있음된) 데이터를 XML 형식으로 데이터 저장소에서 액세스 하는 모든 데이터를 변환 합니다. XML 태그 이름은 데이터 저장소의 열 이름과 최대한 가깝게 일치 합니다.  
  
 사용 하 여 `CXMLAccessor` 적절 하 게 다른 접근자 클래스에 템플릿 매개 변수로 전달 `CCommand` 또는 `CTable`:  
  
```  
CTable<CXMLAccessor, CRowset> rs;  
```  
  
 사용 하 여 [GetXMLRowData](../../data/oledb/cxmlaccessor-getxmlrowdata.md) 하 한 번에 하나의 테이블 행에서 데이터를 검색 하 고 같은 메서드를 사용 하 여 행을 탐색 `MoveNext`, 예:  
  
```  
// Open data source, session, and rowset  
hr = rs.MoveFirst();  

while(SUCCEEDED(hr) && hr != DB_S_ENDOFROWSET )  
{  
    CStringW strRowData;  
    myCmd.GetXMLRowData(strRowData);  
  
    printf_s( "%S\n", strRowData );  
  
    hr = rs.MoveNext();  
}  
```  
  
 사용할 수 있습니다 [GetXMLColumnData](../../data/oledb/cxmlaccessor-getxmlcolumndata.md) XML 형식의 문자열 데이터로 열 (데이터 형식) 정보를 검색 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [접근자 사용](../../data/oledb/using-accessors.md)