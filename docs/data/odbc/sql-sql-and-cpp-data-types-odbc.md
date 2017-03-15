---
title: "SQL: SQL 및 C++ 데이터 형식(ODBC) | Microsoft Docs"
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
  - "데이터 형식[C++], SQL과 C++ 비교"
  - "SQL[C++], C++ 데이터 형식과 비교"
  - "SQL 데이터 형식[C++]"
ms.assetid: 066e0070-d4da-435c-9c4b-f7cab3352c86
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# SQL: SQL 및 C++ 데이터 형식(ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  이 내용은 MFC ODBC 클래스에 적용됩니다.  MFC DAO 클래스를 사용하려면 DAO 도움말의 "Microsoft Jet 데이터베이스 엔진 SQL과 ANSI SQL의 비교" 항목을 참조하십시오.  
  
 다음은 ANSI SQL 데이터 형식을 C\+\+ 데이터 형식으로 매핑한 표입니다.  이 표는 MSDN LIBRARY CD의 *ODBC SDK* *프로그래머 참조*에 있는 부록 D의 C 언어 내용을 보완한 것입니다.  마법사는 대부분의 데이터 형식 매핑을 자동으로 관리합니다.  마법사를 사용하지 않는 경우 해당 매핑 정보를 사용하면 필드 교환 코드를 직접 작성하기가 쉬워집니다.  
  
### C\+\+ 데이터 형식에 매핑되는 ANSI SQL 데이터 형식  
  
|ANSI SQL 데이터 형식|C\+\+ 데이터 형식|  
|---------------------|------------------|  
|**CHAR**|`CString`|  
|**DECIMAL**|`CString` 1|  
|**SMALLINT**|`int`|  
|`REAL`|**float**|  
|**INTEGER**|**long**|  
|**FLOAT**|**double**|  
|**DOUBLE**|**double**|  
|**NUMERIC**|`CString` 1|  
|**VARCHAR**|`CString`|  
|**LONGVARCHAR**|`CLongBinary`, `CString` 2|  
|**BIT**|**BOOL**|  
|**TINYINT**|**BYTE**|  
|**BIGINT**|`CString` 1|  
|**BINARY**|`CByteArray`|  
|**VARBINARY**|`CByteArray`|  
|**LONGVARBINARY**|`CLongBinary`, `CByteArray` 3|  
|**DATE**|`CTime`, `CString`|  
|**TIME**|**CTime, CString**|  
|**TIMESTAMP**|**CTime, CString**|  
  
 1.  **SQL\_C\_CHAR**가 기본 ODBC 전송 형식이기 때문에 ANSI **DECIMAL** 및 **NUMERIC**은 `CString`에 매핑됩니다.  
  
 2.  255자를 넘는 문자 데이터는 `CString`에 매핑될 때 기본값으로 잘립니다.  `RFX_Text`의 `nMaxLength` 인수를 명시적으로 설정하면 잘림 길이를 늘릴 수 있습니다.  
  
 3.  255자를 넘는 이진 데이터는 `CByteArray`에 매핑될 때 기본값으로 잘립니다.  `RFX_Binary`의 `nMaxLength` 인수를 명시적으로 설정하면 잘림 길이를 늘릴 수 있습니다.  
  
 ODBC 커서 라이브러리를 사용하지 않는 경우 Microsoft SQL Server ODBC 드라이버 및 MFC ODBC 데이터베이스 클래스를 사용하여 둘 이상의 긴 가변 길이 필드를 업데이트하려고 하면 문제가 발생할 수 있습니다.  ODBC 형식 **SQL\_LONGVARCHAR** 및 **SQL\_LONGVARBINARY**는 텍스트 및 이미지 SQL 서버 형식으로 매핑됩니다.  동일한 `CRecordset::Update` 호출에서 둘 이상의 긴 가변 길이 필드를 업데이트하면 `CDBException`이 throw됩니다.  따라서 `CRecordset::Update`를 사용하여 여러 개의 긴 열을 동시에 업데이트하면 안 됩니다.  여러 개의 긴 열은 ODBC API **SQLPutData**를 사용하여 동시에 업데이트할 수 있습니다.  ODBC 커서 라이브러리를 사용할 수도 있습니다. 그러나 SQL Server 드라이버처럼 커서를 지원하지만 커서 라이브러리가 필요 없는 드라이버에 대해서는 ODBC 커서 라이브러리를 사용하지 않는 것이 좋습니다.  
  
 MFC ODBC 데이터베이스 클래스 및 Microsoft SQL Server ODBC 드라이버와 함께 ODBC 커서 라이브러리를 사용하는 경우 `CRecordset::Update`를 호출한 다음 `CRecordset::Requery`를 호출하면 `CDBException`과 함께 **ASSERT**가 발생할 수도 있습니다.  그러므로 `CRecordset::Requery` 대신 `CRecordset::Close`를 호출한 다음 `CRecordset::Open`을 호출하는 것이 좋습니다.  다른 해결책은 ODBC 커서 라이브러리를 사용하지 않는 것입니다. SQL Server 및 SQL Server ODBC 드라이버는 기본적으로 커서를 지원하기 때문에 ODBC 커서 라이브러리가 필요하지 않습니다.  
  
## 참고 항목  
 [SQL](../../data/odbc/sql.md)   
 [SQL: SQL 직접 호출\(ODBC\)](../../data/odbc/sql-making-direct-sql-calls-odbc.md)