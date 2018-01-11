---
title: "SQL: SQL 및 c + + 데이터 형식 (ODBC) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- data types [C++], SQL vs. C++
- SQL data types [C++]
- SQL [C++], vs. C++ data types
ms.assetid: 066e0070-d4da-435c-9c4b-f7cab3352c86
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 14afd27887368f07610fb1315d7b573c09382c49
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="sql-sql-and-c-data-types-odbc"></a>SQL: SQL 및 C++ 데이터 형식(ODBC)
> [!NOTE]
>  이 정보는 MFC ODBC 클래스에 적용 됩니다. MFC DAO 클래스와 함께 작업 하는 경우 "비교의 Microsoft Jet 데이터베이스 엔진이 SQL 및 ANSI SQL" DAO 도움말의 항목을 참조 하십시오.  
  
 다음 표에서 c + + 데이터 형식에 ANSI SQL 데이터 형식을 매핑합니다. 부록 D에서 제공 하는 C 언어 정보 강화는 *ODBC SDK* *Programmer's Reference* MSDN 라이브러리 CD에 있습니다. 마법사는 대부분 데이터 형식 매핑을 관리합니다. 마법사를 사용 하지 않는 경우 수동으로 필드 exchange 코드를 작성할 수 있도록 매핑 정보를 사용할 수 있습니다.  
  
### <a name="ansi-sql-data-types-mapped-to-c-data-types"></a>C + + 데이터 형식에 매핑되는 ANSI SQL 데이터 형식  
  
|ANSI SQL 데이터 형식|C++ 데이터 형식|  
|------------------------|---------------------|  
|**CHAR**|`CString`|  
|**DECIMAL**|`CString` 1|  
|**SMALLINT**|`int`|  
|`REAL`|**float**|  
|**정수**|**long**|  
|**FLOAT**|**double**|  
|**DOUBLE**|**double**|  
|**숫자**|`CString` 1|  
|**VARCHAR**|`CString`|  
|**LONGVARCHAR**|`CLongBinary`, `CString` 2|  
|**비트**|**BOOL**|  
|**TINYINT**|**BYTE**|  
|**BIGINT**|`CString` 1|  
|**이진**|`CByteArray`|  
|**VARBINARY**|`CByteArray`|  
|**LONGVARBINARY**|`CLongBinary`, `CByteArray` 3|  
|**DATE**|`CTime`, `CString`|  
|**시간**|**CTime, CString**|  
|**타임 스탬프**|**CTime, CString**|  
  
 1. ANSI **10 진수** 및 **숫자** 매핑됩니다 `CString` 때문에 **SQL_C_CHAR** 기본 ODBC 전송 유형입니다.  
  
 2. 에 매핑할 때 기본적으로 255 자 넘는 문자 데이터는 잘립니다 `CString`합니다. 명시적으로 설정 하 여 잘림을 길이 확장할 수 있습니다는 `nMaxLength` 의 인수 `RFX_Text`합니다.  
  
 3. 에 매핑할 때 기본적으로 255 자 초과 하 여 이진 데이터는 잘립니다 `CByteArray`합니다. 명시적으로 설정 하 여 잘림을 길이 확장할 수 있습니다는 `nMaxLength` 의 인수 `RFX_Binary`합니다.  
  
 ODBC 커서 라이브러리를 사용 하지 않는 경우 Microsoft SQL Server ODBC 드라이버와 MFC ODBC 데이터베이스 클래스를 사용 하 여 더 많은 긴 가변 길이 필드 또는 두 개를 업데이트 하려고 할 때 문제가 발생할 수 있습니다. ODBC 형식 **SQL_LONGVARCHAR** 및 **SQL_LONGVARBINARY**, 텍스트에 지도 및 이미지 SQL Server 형식입니다. A `CDBException` 동일한 호출에서 두 개 이상의 긴 가변 길이 필드를 업데이트 하는 경우 throw 되 `CRecordset::Update`합니다. 따라서와 동시에 여러 개의 긴 열을 업데이트 하지 않으면 `CRecordset::Update`합니다. ODBC API로 동시에 여러 개의 긴 열을 업데이트할 수 있습니다 **SQLPutData**합니다. ODBC 커서 라이브러리를 사용할 수도 있지만이 커서를 지원 하 고 커서 라이브러리 불필요 하는 드라이버에서 SQL Server 드라이버와 같은 권장 되지 않습니다.  
  
 MFC ODBC 데이터베이스 클래스와 Microsoft SQL Server ODBC 드라이버는 ODBC 커서 라이브러리를 사용 하는 경우는 **ASSERT** 와 함께 발생할 수 있습니다는 `CDBException` 호출 하는 경우 `CRecordset::Update` 호출한 `CRecordset::Requery`합니다. 대신, 호출 `CRecordset::Close` 및 `CRecordset::Open` 대신 `CRecordset::Requery`합니다. ODBC 커서 라이브러리를 사용 하지는 다른 솔루션은입니다.  
  
## <a name="see-also"></a>참고 항목  
 [SQL](../../data/odbc/sql.md)   
 [SQL: SQL 직접 호출(ODBC)](../../data/odbc/sql-making-direct-sql-calls-odbc.md)