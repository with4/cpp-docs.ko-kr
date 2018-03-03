---
title: "SQL Server에 안정형 어셈블리 사용 (C + + /cli CLI) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- verifiable assemblies [C++], with SQL Server
ms.assetid: 5248a60d-aa88-4ff3-b30a-b791c3ea2de9
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: d03d54dd52f95f3fbba35bb896594e90aa92e867
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="using-verifiable-assemblies-with-sql-server-ccli"></a>SQL Server에 안정형 어셈블리 사용(C++/CLI)
동적 연결 라이브러리 (Dll)로 패키지 하는 확장된 저장된 프로시저에는 Visual c + +를 사용 하 여 개발 하는 기능을 통해 SQL Server 기능을 확장 하는 방법을 제공 합니다. 확장된 저장된 프로시저 Dll 내에서 함수로 구현 됩니다. 함수 외에 확장된 저장된 프로시저를 정의할 수도 [사용자 정의 형식](../cpp/classes-and-structs-cpp.md) 및 [집계 함수는](http://msdn.microsoft.com/en-us/de255454-f45e-4281-81f9-bc61893ac5da) (예: SUM 또는 AVG).  
  
 클라이언트가 확장된 저장된 프로시저를 실행할 때 SQL Server DLL에 대 한 확장된 저장된 프로시저와 관련 된 검색과 해당 DLL을 로드 합니다. SQL Server는 요청 된 확장된 저장된 프로시저를 호출 하 고 지정 된 보안 컨텍스트 내에서 실행 합니다. 확장 저장 프로시저는 전달 결과 집합 및 매개 변수를 서버에 다시 반환 합니다.  
  
 [!INCLUDE[sqprsqlong](../dotnet/includes/sqprsqlong_md.md)]transact-sql에 (T-SQL) SQL Server에 안정형 어셈블리를 설치할 수 있도록 확장을 제공 합니다. SQL Server 사용 권한 집합에는 다음과 같은 수준의 보안으로 보안 컨텍스트를 지정합니다.  
  
-   무제한 모드:; 위험은 사용자가 코드를 실행 합니다. 코드 형식 안전성이 없는 합니다.  
  
-   안전 모드: 형식이 안전한 코드를 실행 /clr: safe로 컴파일됩니다.  
  
 안전 모드에서는 실행 된 어셈블리를 확인할 수 있는 형식 안전에 있습니다.  
  
 를 만들고 SQL Server에 안정형 어셈블리를 로드 하려면 다음과 같이 CREATE ASSEMBLY 및 DROP ASSEMBLY TRANSACT-SQL 명령을 사용.  
  
```  
CREATE ASSEMBLY <assemblyName> FROM <'Assembly UNC Path'> WITH   
  PERMISSION_SET <permissions>  
DROP ASSEMBLY <assemblyName>  
```  
  
 PERMISSION_SET 명령은 보안 컨텍스트를 지정 하 고 제한 없음, 안전 하 게 또는 확장 값을 가질 수 있습니다.  
  
 또한 클래스에서 메서드 이름에 바인딩할 CREATE FUNCTION 명령을 사용할 수 있습니다.  
  
```  
CREATE FUNCTION <FunctionName>(<FunctionParams>)  
RETURNS returnType  
[EXTERNAL NAME <AssemblyName>:<ClassName>::<StaticMethodName>]  
```  
  
## <a name="example"></a>예  
 SQL Server에 어셈블리를 로드 하 고 클래스의 메서드를 사용할 수 있도록 하는 다음 SQL 스크립트 (예를 들어 명명 된 "MyScript.sql").  
  
```  
-- Create assembly without external access  
drop assembly stockNoEA  
go  
create assembly stockNoEA  
from   
'c:\stockNoEA.dll'  
with permission_set safe  
  
-- Create function on assembly with no external access  
drop function GetQuoteNoEA  
go  
create function GetQuoteNoEA(@sym nvarchar(10))  
returns real  
external name stockNoEA:StockQuotes::GetQuote  
go  
  
-- To call the function  
select dbo.GetQuoteNoEA('MSFT')  
go  
```  
  
 SQL 쿼리 분석기 또는 sqlcmd.exe 유틸리티를 사용 하 여 명령줄에서 SQL 스크립트를 대화형으로 실행할 수 있습니다. 다음 명령줄 MyServer 연결, 기본 데이터베이스를 사용 하 여, 트러스트 된 연결을 사용 하 여, MyScript.sql, 입력 및 MyResult.txt를 출력 합니다.  
  
```  
sqlcmd -S MyServer -E -i myScript.sql -o myResult.txt  
```  
  
## <a name="see-also"></a>참고 항목  
 [방법: /clr: safe로 마이그레이션 (C + + /cli CLI)](../dotnet/how-to-migrate-to-clr-safe-cpp-cli.md)   
 [클래스 및 구조체](../cpp/classes-and-structs-cpp.md)