---
title: "db_column | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.db_column"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "db_column attribute"
ms.assetid: 58da4afc-f69c-4ae6-af9a-3f9515f56081
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# db_column
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

지정 된 열 행 집합에서을 변수에 바인딩합니다.  
  
## 구문  
  
```  
  
      [ db_column(   
   ordinal,   
   dbtype,   
   precision,   
   scale,   
   status,   
   length   
) ]  
```  
  
#### 매개 변수  
 `ordinal`  
 서 수 열 번호 \(**DBCOLUMNINFO** 서 수\) 또는 열 이름에 해당 하는 행 집합에 데이터를 바인딩할 필드 \(ANSI 또는 유니코드 문자열\)입니다.  숫자를 사용 하는 경우 연속 된 서 수를 건너뛸 수 있습니다 \(예: 1, 2, 3, 5\).  사용 하는 OLE DB 공급자에서 지 원하는 경우 공백이 포함 될 수 있습니다.  예를 들어, 다음 형식 중 하나를 사용할 수 있습니다.  
  
```  
[db_column("2")] TCHAR szCity[30];  
[db_column(L"city_name")] TCHAR szCity[30];  
```  
  
 *dbtype*  \(옵션\)  
 OLE DB  [형식 표시기](https://msdn.microsoft.com/en-us/library/ms711251.aspx) 열 항목에 대 한.  
  
 *정밀도*  \(옵션\)  
 열 항목을 사용할 수 전체 자릿수입니다.  에 대 한 자세한 내용은 `bPrecision` 의 요소는  [DBBINDING 구조](https://msdn.microsoft.com/en-us/library/ms716845.aspx)  
  
 *배율*  \(옵션\)  
 열 항목을 사용할 수 소수입니다.  에 대 한 자세한 내용은 `bScale` 의 요소는  [DBBINDING 구조](https://msdn.microsoft.com/en-us/library/ms716845.aspx)  
  
 *상태*  \(옵션\)  
 멤버 변수 상태가이 열에 저장 하는 데 사용 합니다.  상태 열의 값에 데이터 값 또는 다른 값을 같은 인지 여부를 나타내는  **NULL**.  가능한 값에 대 한  [상태](https://msdn.microsoft.com/en-us/library/ms722617.aspx) 에 있는  *OLE DB 프로그래머용 참조*.  
  
 *길이*  \(옵션\)  
 멤버 변수는 열의 크기를 바이트 단위로 저장 하는 데 있습니다.  
  
## 설명  
 **db\_column** 변수 행 집합에 지정 된 테이블이 열에 바인딩합니다.  OLE DB에서 참여할 수 있는 구성원 데이터 구분 `IAccessor`\-바인딩을 기반으로 합니다.  일반적으로 OLE DB 소비자 매크로 사용 하 여 정의 된 열 맵까지이 특성을 설정 합니다.  [BEGIN\_COLUMN\_MAP](../data/oledb/begin-column-map.md),  [END\_COLUMN\_MAP](../data/oledb/end-column-map.md), 및  [COLUMN\_ENTRY](../data/oledb/column-entry.md).  이러한 OLE DB 조작  [DBBINDING 구조](https://msdn.microsoft.com/en-us/library/ms716845.aspx) 지정 된 열에 바인딩할 수 있습니다.  표시 하면 각 멤버는  **db\_column** 특성이 차지 항목이 열 맵 형식으로 열의 항목에에서.  따라서, 위치를 열 맵을, 명령 또는 테이블 클래스에서 추가 하면이 특성을 호출 합니다.  
  
 사용  **db\_column** 함께 하나는  [db\_table](../windows/db-table.md) 또는  [db\_command](../windows/db-command.md) 특성입니다.  
  
 소비자 특성 공급자 클래스에이 특성을 적용 하는 경우 컴파일러는 클래스 이름을 \_ 하*YourClassName*접근자를 위치  *YourClassName* 클래스를 제공한 이름입니다 및 컴파일러도 라는 클래스를 만듭니다  *YourClassName,*  \_에서 파생 되는*YourClassName*접근자입니다.  클래스 뷰에서 클래스 모두에 표시 됩니다.  
  
 샘플 응용 프로그램에서 사용 되는이 특성의 예를 참조 하십시오  [AtlAgent](http://msdn.microsoft.com/ko-kr/52bef5da-c1a0-4223-b4e6-9e464b6db409), 및  [MultiRead](http://msdn.microsoft.com/ko-kr/5a2a915a-77dc-492f-94b2-1b809995dd5e).  
  
## 예제  
 이 예제 테이블에 열을 바인딩할는  **긴** 데이터 멤버 및 상태와 길이 필드를 지정 합니다.  
  
```  
// db_column_1.cpp  
// compile with: /LD  
#include <atlbase.h>  
#include <atlplus.h>  
#include <atldbcli.h>  
  
[ db_command(L"Select * from Products") ]  
class CProducts {  
   DBSTATUS m_dwProductIDStatus;  
   DBLENGTH m_dwProductIDLength;  
  
   [ db_column("1", status="m_dwProductIDStatus", length="m_dwProductIDLength") ] LONG m_ProductID;  
};  
```  
  
## 예제  
 이 샘플에서는 네 개의 열에 바인딩하는  **긴**, 문자열, 타임 스탬프, a  **DB\_NUMERIC** 정수를 순서 대로.  
  
```  
// db_column_2.cpp  
// compile with: /LD  
#include <atlbase.h>  
#include <atlplus.h>  
#include <atldbcli.h>  
  
[ db_command(L"Select * from Products") ]  
class CProducts {  
   [db_column("1")] LONG m_OrderID;  
   [db_column("2")] TCHAR m_CustomerID[6];  
   [db_column("4")] DB_NUMERIC m_OrderDate;     
   [db_column("7", dbtype="DBTYPE_NUMERIC")] DB_NUMERIC m_ShipVia;  
};  
```  
  
## 요구 사항  
  
### 컨텍스트 특성  
  
|||  
|-|-|  
|**적용 대상**|**클래스**, `struct`, 멤버, 메서드|  
|**반복 가능**|아니요|  
|**필수 특성**|없음|  
|**잘못 된 특성**|없음|  
  
 속성 컨텍스트에 대 한 자세한 내용은 참조 하십시오.  [컨텍스트 특성](../windows/attribute-contexts.md).  
  
## 참고 항목  
 [OLE DB Consumer Attributes](../windows/ole-db-consumer-attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/ko-kr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)