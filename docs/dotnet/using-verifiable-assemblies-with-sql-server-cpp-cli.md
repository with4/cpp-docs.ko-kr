---
title: "SQL Server에 안정형 어셈블리 사용(C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "안정형 어셈블리[C++], SQL Server"
ms.assetid: 5248a60d-aa88-4ff3-b30a-b791c3ea2de9
caps.latest.revision: 21
caps.handback.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# SQL Server에 안정형 어셈블리 사용(C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

DLL\(동적 연결 라이브러리\)로 패키징되는 확장 저장 프로시저를 사용하면 [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)]로 개발한 함수를 통해 SQL Server 기능을 확장할 수 있습니다.  확장 저장 프로시저는 DLL 내에서 함수로 구현됩니다.  함수 이외에도 확장 저장 프로시저는 [사용자 정의 형식](../cpp/classes-and-structs-cpp.md)과 SUM 또는 AVG 같은 [집계 함수](http://msdn.microsoft.com/ko-kr/de255454-f45e-4281-81f9-bc61893ac5da)를 정의할 수 있습니다.  
  
 클라이언트에서 확장 저장 프로시저를 실행하면 SQL Server는 확정 저장 프로시저에 관련된 DLL을 검색하여 이 DLL을 로드합니다.  SQL Server는 요청된 확장 저장 프로시저를 호출하고 지정된 보안 컨텍스트에서 이를 실행합니다.  그런 다음 확장 저장 프로시저는 결과 집합을 전달하고 매개 변수를 서버에 다시 반환합니다.  
  
 [!INCLUDE[sqprsqlong](../dotnet/includes/sqprsqlong_md.md)]에서는 SQL Server에 안정형 어셈블리를 설치할 수 있도록 T\-SQL\(Transact\-SQL\)에 대한 확장을 제공합니다.  SQL Server 권한 집합에서는 다음과 같은 수준의 보안으로 보안 컨텍스트를 지정합니다.  
  
-   무제한 모드: 코드를 실행하는 데 위험이 따릅니다. 코드가 안정형 형식이 안전한 코드가 아닐 수 있습니다.  
  
-   안전 모드: \/clr:safe를 사용하여 컴파일된 안정형 형식이 안전한 코드를 실행합니다.  
  
 안전 모드에서는 실행되는 어셈블리가 안정형 형식이 안전한 어셈블리여야 합니다.  
  
 안정형 어셈블리를 만들고 SQL Server에 로드하려면 다음과 같이 Transact\-SQL 명령 CREATE ASSEMBLY 및 DROP ASSEMBLY를 사용합니다.  
  
```  
CREATE ASSEMBLY <assemblyName> FROM <'Assembly UNC Path'> WITH   
  PERMISSION_SET <permissions>  
DROP ASSEMBLY <assemblyName>  
```  
  
 PERMISSION\_SET 명령은 보안 컨텍스트를 지정합니다. 값으로 UNRESTRICTED, SAFE 또는 EXTENDED를 사용할 수 있습니다.  
  
 또한 CREATE FUNCTION 명령을 사용하여 클래스의 메서드 이름에 바인딩할 수 있습니다.  
  
```  
CREATE FUNCTION <FunctionName>(<FunctionParams>)  
RETURNS returnType  
[EXTERNAL NAME <AssemblyName>:<ClassName>::<StaticMethodName>]  
```  
  
## 예제  
 예를 들어, "MyScript.sql"이라는 다음과 같은 SQL 스크립트에서는 어셈블리를 SQL Server에 로드하고 클래스의 메서드를 사용할 수 있도록 만듭니다.  
  
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
  
 SQL Query Analyzer에서 또는 sqlcmd.exe 유틸리티를 사용하여 명령줄에서 SQL 스크립트를 대화형으로 실행할 수 있습니다.  다음 명령줄에서는 MyServer에 연결하고, 기본 데이터베이스를 사용하고, 신뢰할 수 있는 연결을 사용하고, MyScript.sql을 입력하고, MyResult.txt를 출력합니다.  
  
```  
sqlcmd –S MyServer -E –i myScript.sql –o myResult.txt  
```  
  
## 참고 항목  
 [방법: \/clr:safe로 마이그레이션](../dotnet/how-to-migrate-to-clr-safe-cpp-cli.md)   
 [클래스 및 구조체](../cpp/classes-and-structs-cpp.md)