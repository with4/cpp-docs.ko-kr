---
title: "OLE DB 프로그래밍 개요 | Microsoft Docs"
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
  - "OLE DB, OLE DB 정보"
  - "범용 데이터 액세스"
ms.assetid: a5a69730-2793-4277-a67d-6f3c8edab6df
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# OLE DB 프로그래밍 개요
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OLE DB란 무엇이며 다른 데이터베이스 기술과는 어떤 차이점이 있을까요?  OLE DB란 Microsoft에서 개발한 고성능 COM 기반 데이터베이스 기술입니다.  Microsoft의 다른 데이터베이스 기술과 OLE DB가 다른 점은 OLE DB에서는 Universal Data Access를 제공한다는 것입니다.  
  
## Universal Data Access  
 Universal Data Access는 데이터가 저장된 형식에 상관없이 데이터에 액세스할 수 있는 일반적인 방법을 제공합니다.  일반적인 업무 상황에서 방대한 양의 정보가 기업 데이터베이스 외부에 저장됩니다.  이러한 정보는 파일 시스템\(예: FAT 또는 NTFS\), 순차 색인 파일, 개인 데이터베이스\(예: Access\), 스프레드시트\(예: Excel\), 프로젝트 계획 응용 프로그램\(예: Project\), 전자 메일\(예: Outlook\) 등에 들어 있습니다.  
  
 관련된 다양한 응용 프로그램을 사용하여 이러한 데이터에 액세스하면 워크플로 상에 상당한 병목 현상이 나타나거나 문제가 발생하게 됩니다.  현재 대부분의 기업은 이러한 현상을 자주 겪고 있으며, 데이터베이스 관리 시스템\(DBMS\)에서 정보를 통합하는 방법으로 문제를 처리하고 있습니다.  그러나 이러한 작업은 비용과 시간이 많이 들어 실용적이라고 할 수 없습니다.  
  
 그에 대한 대안이 바로 Universal Data Access 솔루션을 개발하는 것입니다.  OLE DB 및 ADO에서는 Universal Data Access 기능을 제공하고 있습니다.  두 가지 기능 중에서 OLE DB의 성능이 더 강력하며 Visual C\+\+ 응용 프로그램과 함께 사용하기에 좋습니다.  
  
 Universal Data Access에는 두 가지 기능이 포함되어 있습니다. 첫 번째 기능은 다중\(분산\) 데이터 소스에 대한 분산 쿼리 또는 일정한 방식의 액세스이며, 두 번째 기능은 DBMS가 아닌 데이터 소스가 데이터베이스 응용 프로그램에 액세스할 수 있게 만들어 주는 기능입니다.  
  
-   분산 쿼리  
  
     다중\(분산\) 데이터 소스에서 일정한 방식으로 데이터에 액세스할 수 있는 기능입니다.  데이터 소스는 두개의 개별적인 Access 데이터베이스 같이 같은 형식이거나 SQL Server 데이터베이스와 Access 데이터베이스 같이 서로 다른 형식일 수 있습니다.  일정한 방식이라는 말은 모든 데이터 소스에서 같은 쿼리를 의미있게 실행할 수 있다는 의미입니다.  
  
-   비 DBMS 액세스  
  
     DBMS가 아닌 데이터 소스에서 데이터베이스 응용 프로그램에 액세스할 수 있게 만들어 주는 기능입니다.  DBMS 데이터 소스의 예제로는 IMS, DB2, Oracle, SQL Server, Access 및 Paradox가 있습니다.  DBMS가 아닌 데이터 소스의 예제로는 파일 시스템, 전자 메일, 스프레드시트, 프로젝트 관리 도구 등의 정보가 포함됩니다.  
  
 영업 부서에서 특정 기간 동안 고객에게서 일주일 동안 받은 모든 전자 메일 메시지가 필요하게 된 경우를 가정해 봅시다.  이 쿼리를 위해서는 전자 메일 응용 프로그램의 사서함 파일을 모두 검색하고 고객의 이름을 지정한 고객의 Access 테이블을 검색해야 합니다.  Access는 DBMS 응용 프로그램이지만 Outlook은 DBMS 응용 프로그램이 아닙니다.  
  
 OLE DB를 사용하면 데이터 소스가 DBMS 데이터 소스인지의 여부와 상관없이 여러 데이터 소스에 액세스하는 응용 프로그램을 개발할 수 있습니다.  OLE DB는 주어진 데이터 소스에 알맞은 DBMS 기능을 지원하는 COM 인터페이스를 사용하는 방법으로 universal access를 가능하게 해 줍니다.  COM은 불필요한 서비스 중복을 감소시키며, 데이터 소스뿐만 아니라 다른 응용 프로그램 사이에서 상호 운용성을 극대화합니다.  
  
## COM의 장점  
 COM에 대한 설명으로 시작해 봅시다.  OLE DB는 COM 인터페이스의 집합입니다.  사용자는 일정한 인터페이스 집합을 통해 데이터에 액세스하여 데이터베이스를 구성 요소 조합 매트릭스로 구성할 수 있습니다.  
  
 COM 사양을 바탕으로, OLE DB는 DBMS 기능의 지속적이고 다시 사용할 수 있는 부분을 요소로 가지고 있고 캡슐화하는 인터페이스의 확장 가능하고 유지 가능한 컬렉션을 정의합니다.  이러한 인터페이스는 여러 정보 소스에 대한 일정한 방식의 트랜잭션 액세스를 가능하게 해 주는 행 컨테이너, 쿼리 프로세서 및 트랜잭션 코디네이터 같은 DBMS 구성 요소의 경계를 정의합니다.  
  
 보통 OLE DB 응용 프로그램은 DLL로 작성되지만, COM을 구현하면 구성 요소화된 코드를 사용하여 이름 지정 및 버전 문제와 같은 DLL의 단점을 극복합니다.  OLE DB에서는 GUID\(Globally Unique Identifier\)를 사용하여 인터페이스를 호출하거나 다른 구성 요소에 액세스합니다.  
  
 마지막으로, COM은 참조 횟수를 사용하여 구성 요소 사용을 추적합니다.  인터페이스에서 메서드를 호출하면 참조 횟수가 증가되고, 메서드를 반환하면 참조 횟수가 줄어듭니다.  참조 횟수가 0이 되면, 메서드가 속한 구성 요소는 릴리스됩니다.  
  
## 참고 항목  
 [OLE DB 프로그래밍](../../data/oledb/ole-db-programming.md)   
 [OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB 템플릿](../../data/oledb/ole-db-templates.md)