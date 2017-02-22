---
title: "db_param | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.db_param"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "db_param attribute"
ms.assetid: a28315f5-4722-459e-92ef-32e83c0b205a
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# db_param
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

지정 된 멤버 변수는 입력 또는 출력 매개 변수를 연결 하 고 변수를 구분 합니다.  
  
## 구문  
  
```  
  
      [ db_param(   
   ordinal,   
   paramtype="DBPARAMIO_INPUT",   
   dbtype,   
   precision,   
   scale,   
   status,   
   length  
) ]  
```  
  
#### 매개 변수  
 `ordinal`  
 열 번호 \(**DBCOLUMNINFO** 서 수\)에 해당 하는 행 집합에 데이터를 바인딩할 필드입니다.  
  
 *paramtype*  \(옵션\)  
 매개 변수를 설정 하는 형식입니다.  공급자는 데이터 원본에서 지원 되는 매개 변수 I\/O 형식만 지원 합니다.  종류는 하나 이상의 조합입니다  **DBPARAMIOENUM** 값:  
  
-   **DBPARAMIO\_INPUT** 입력된 매개 변수입니다.  
  
-   **DBPARAMIO\_OUTPUT** 출력 매개 변수입니다.  
  
-   **DBPARAMIO\_NOTPARAM** 는 접근자에 매개 변수가 없습니다.  설정  **eParamIO** 이 행의이 값을 접근자 기억 사용자 매개 변수는 무시 됩니다.  
  
 *dbtype*  \(옵션\)  
 OLE DB  [형식 표시기](https://msdn.microsoft.com/en-us/library/ms711251.aspx) 열 항목에 대 한.  
  
 *정밀도*  \(옵션\)  
 열 항목을 사용할 수 전체 자릿수입니다.  에 대 한 자세한 내용은  **bPrecision** 의 요소는  [DBBINDING 구조](https://msdn.microsoft.com/en-us/library/ms716845.aspx)  
  
 *배율*  \(옵션\)  
 열 항목을 사용할 수 소수입니다.  에 대 한 자세한 내용은  **bScale** 의 요소는  [DBBINDING 구조](https://msdn.microsoft.com/en-us/library/ms716845.aspx)  
  
 *상태*  \(옵션\)  
 멤버 변수 상태가이 열에 저장 하는 데 사용 합니다.  상태 열의 값에 데이터 값 또는 다른 값을 같은 인지 여부를 나타내는  **NULL**.  가능한 값에 대 한  [상태](https://msdn.microsoft.com/en-us/library/ms722617.aspx) 에 있는  *OLE DB 프로그래머용 참조*.  
  
 *길이*  \(옵션\)  
 멤버 변수는 열의 크기를 바이트 단위로 저장 하는 데 있습니다.  
  
## 설명  
 **db\_param** ; 명령에 사용할 매개 변수를 정의 합니다. 따라서 함께 사용 하 여  **db\_command**.  예를 들어, 사용할 수 있습니다  **db\_param** SQL 쿼리 또는 저장된 프로시저에서 매개 변수를 바인딩할 수 있습니다.  물음표 \(?\) 매개 변수는 저장된 프로시저에 표시 됩니다 및 데이터 멤버에 매개 변수가 나타나는 순서 대로 연결 되어야 합니다.  
  
 **db\_param** OLE DB에서 참여할 수 있는 구성원 데이터를 구분 합니다. `ICommandWithParameters`\-바인딩을 기반으로 합니다.  매개 변수 형식 \(입력 또는 출력\), OLE DB 형식, 정밀도, 배율, 상태 및 지정 된 매개 변수의 길이 설정 합니다.  BEGIN\_PARAM\_MAP는 OLE DB 소비자 매크로 삽입합니다.이 특성...  END\_PARAM\_MAP입니다.  표시 하면 각 멤버는  **db\_param** 특성이 차지 항목이 맵에 COLUMN\_ENTRY의 형태로.  
  
 **db\_param** 하나 하 나와 함께 사용 되는  [db\_table](../windows/db-table.md) 또는  [db\_command](../windows/db-command.md) 특성입니다.  
  
 소비자 특성 공급자 클래스에이 특성을 적용 하는 경우 컴파일러는 클래스 이름을 \_ 하*YourClassName*접근자를 위치  *YourClassName* 클래스를 제공한 이름입니다 및 컴파일러도 라는 클래스를 만듭니다  *YourClassName,*  \_에서 파생 되는*YourClassName*접근자입니다.  클래스 뷰에서 클래스 모두에 표시 됩니다.  
  
## 예제  
 SalesbyYear 저장 프로시저는 Northwind 데이터베이스에서를 기반으로 명령 클래스를 만드는 예제입니다.  첫 번째 매개 변수를 저장된 프로시저에 연결의 `m_RETURN_VALUE` 변수를 출력 매개 변수로 정의 합니다.  마지막 두 \(입력된\) 매개 변수를 연결 `m_Beginning_Date` 및 `m_Ending_Date`.  
  
 다음 예제에서는 연결을 `nOutput` 출력 매개 변수입니다.  
  
```  
// db_param.cpp  
// compile with: /LD  
#include <atlbase.h>  
#include <atlplus.h>  
#include <atldbcli.h>  
  
[ db_source(L"my_connection_string"),   
  db_command(L"{ ? = CALL dbo.\"Sales by Year\"(?,?) }")   
]  
struct CSalesbyYear {  
   DBSTATUS m_dwShippedDateStatus;  
   DBSTATUS m_dwOrderIDStatus;  
   DBSTATUS m_dwSubtotalStatus;  
   DBSTATUS m_dwYearStatus;  
  
   DBLENGTH m_dwShippedDateLength;  
   DBLENGTH m_dwOrderIDLength;  
   DBLENGTH m_dwSubtotalLength;  
   DBLENGTH m_dwYearLength;  
  
   // Bind columns  
   [ db_column("1", status="m_dwShippedDateStatus", length="m_dwShippedDateLength") ] DBTIMESTAMP m_ShippedDate;  
   [ db_column("2", status="m_dwOrderIDStatus", length="m_dwOrderIDLength") ] LONG m_OrderID;  
   [ db_column("3", status="m_dwSubtotalStatus", length="m_dwSubtotalLength") ] CURRENCY m_Subtotal;  
   [ db_column("4", status="m_dwYearStatus", length="m_dwYearLength") ] TCHAR m_Year[31];  
  
   // Bind parameters  
   [ db_param("1", paramtype="DBPARAMIO_OUTPUT") ] LONG m_RETURN_VALUE;  
   [ db_param("2", paramtype="DBPARAMIO_INPUT") ] DBTIMESTAMP m_Beginning_Date;  
   [ db_param("3", paramtype="DBPARAMIO_INPUT") ] DBTIMESTAMP m_Ending_Date;  
};  
```  
  
## 요구 사항  
  
### 컨텍스트 특성  
  
|||  
|-|-|  
|**적용 대상**|**클래스**, `struct`, 멤버, 메서드, 현지|  
|**반복 가능**|아니요|  
|**필수 특성**|없음|  
|**잘못 된 특성**|없음|  
  
 속성 컨텍스트에 대 한 자세한 내용은 참조 하십시오.  [컨텍스트 특성](../windows/attribute-contexts.md).  
  
## 참고 항목  
 [OLE DB Consumer Attributes](../windows/ole-db-consumer-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/ko-kr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)