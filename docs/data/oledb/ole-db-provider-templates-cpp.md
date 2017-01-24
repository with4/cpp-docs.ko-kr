---
title: "OLE DB 공급자 템플릿(C++) | Microsoft Docs"
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
  - "데이터베이스[C++], OLE DB 템플릿"
  - "OLE DB 공급자 템플릿[C++], OLE DB 공급자 템플릿 정보"
  - "OLE DB 공급자[C++], 공급자 정보"
  - "템플릿[C++], OLE DB"
ms.assetid: fccff85f-2af8-4500-82bd-6312d28a74b8
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# OLE DB 공급자 템플릿(C++)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OLE DB는 Microsoft의 범용 데이터 액세스 전략의 중요한 부분을 차지합니다.  OLE DB의 디자인은 모든 데이터 소스에서 뛰어난 데이터 액세스를 가능하게 합니다.  테이블 형식 데이터의 경우 데이터베이스의 데이터인지에 상관없이 OLE DB를 통해 볼 수 있습니다.  이러한 융통성은 뛰어난 성능을 제공합니다.  
  
 [OLE DB 소비자 및 공급자](../../data/oledb/ole-db-consumers-and-providers.md)에서 설명한 대로 OLE DB는 소비자와 공급자의 개념을 사용합니다.  소비자는 데이터를 요청하고 공급자는 소비자에게 테이블 형식으로 데이터를 반환합니다.  프로그래밍 측면에서 이 모델의 가장 중요한 점은 소비자가 만드는 모든 호출을 공급자가 구현해야 한다는 점입니다.  
  
## 공급자 정의  
 OLE DB 공급자는 데이터 저장소라고 하는 영구적인 소스의 데이터를 테이블 형식으로 소비자에게 전달함으로써 소비자 개체로부터의 인터페이스 호출을 처리하는 COM 개체들의 집합입니다.  
  
 공급자는 단순하기도 하고 복잡하기도 합니다.  공급자는 최소한의 기능을 지원할 수도 있고 보다 많은 인터페이스를 구현하여 완전한 제품 품질을 갖춘 공급자를 지원할 수도 있습니다.  공급자는 테이블을 반환할 수도 있고 클라이언트가 테이블 형식을 결정하도록 할 수도 있고 해당 데이터에 대한 작업을 수행할 수도 있습니다.  
  
 각 공급자는 표준 COM 개체 집합을 구현하여 클라이언트의 요청을 처리합니다. 여기서 표준이란 언어\(C\+\+, Basic 등\)에 관계없이 모든 OLE DB 소비자가 모든 공급자의 데이터에 액세스할 수 있다는 것을 의미합니다.  
  
 각 COM 개체에는 인터페이스가 몇 개씩 포함되어 있으며, 이 중 일부는 필수이고 일부는 선택적입니다.  공급자는 필수 인터페이스를 구현하여 모든 클라이언트가 사용할 수 있는 최소 수준의 기능\(요건 충족\)을 보장합니다.  또한 선택적 인터페이스를 구현하여 추가 기능을 제공할 수 있습니다.  [OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)에서 이 인터페이스에 대해 자세히 설명합니다.  공급자가 해당 인터페이스를 지원하는지 확인하려면 클라이언트가 항상 `QueryInterface`를 호출해야 합니다.  
  
## OLE DB 사양 수준 지원  
 OLE DB 공급자 템플릿은 OLE DB 버전 2.7 사양을 지원합니다.  OLE DB 공급자 템플릿을 사용하여 수준 0과 호환이 되는 공급자를 구현할 수 있습니다.  예를 들어, 공급자 샘플은 DOS DIR 명령을 실행하여 파일 시스템을 쿼리하는 SQL이 아닌\(MS\-DOS\) 명령 서버를 구현하기 위해 템플릿을 사용합니다.  공급자 샘플은 테이블 형식 데이터를 반환하기 위한 표준 OLE DB 메커니즘인 행 집합에 디렉터리 정보를 반환합니다.  
  
 OLE DB 템플릿이 지원하는 가장 단순한 공급자는 명령이 없는 읽기 전용 공급자입니다.  책갈피 설정과 읽기\/쓰기 기능과 같은 명령이 있는 공급자도 지원됩니다.  읽기\/쓰기 공급자는 추가 코드를 작성하여 구현할 수 있습니다.  현재 버전에서는 동적 행 집합과 트랜잭션이 지원되지 않지만 필요하면 추가할 수 있습니다.  
  
## OLE DB 공급자를 만들어야 할 시기  
 Microsoft Visual C\+\+에는 **데이터 연결 속성** 대화 상자에 몇 가지 미리 패키지된 표준 공급자가 제공되므로 항상 직접 공급자를 만들 필요가 없습니다.  OLE DB 공급자를 만드는 주요한 이유는 범용 데이터 액세스 전략을 이용하려는 데 있습니다.  범용 데이터 액세스 전략을 이용할 경우 얻을 수 있는 이점은 다음과 같습니다.  
  
-   C\+\+, Basic, Visual Basic 스크립팅 버전 등 모든 언어를 통해 데이터 액세스.  사용하는 언어에 관계없이 조직의 여러 프로그래머가 같은 방법으로 같은 데이터에 액세스할 수 있습니다.  
  
-   SQL Server, Excel 및 Access 같은 다른 데이터 소스에 데이터 노출.  여러 형식으로 된 데이터를 전송하려는 경우 아주 유용합니다.  
  
-   서로 다른\(유형이 다른\) 데이터 소스 작업에 참여.  데이터 웨어하우징을 위한 효과적인 방법입니다.  OLE DB 공급자를 사용하여 원시 형식으로 데이터를 보관하고 간단한 작업으로 데이터에 액세스할 수 있습니다.  
  
-   쿼리 처리와 같은 추가 기능을 데이터에 추가  
  
-   데이터 조작 방법을 제어하여 데이터 액세스 성능 증대  
  
-   견고성 증대.  한 프로그래머만 액세스할 수 있는 독점적 데이터 형식이 있으면 위험합니다.  OLE DB 공급자를 사용하면 모든 프로그래머에게 독점적 형식을 공개할 수 있습니다.  
  
## 읽기 전용 공급자 및 업데이트 가능 공급자  
 공급자마다 그 복잡도와 기능이 많이 다르므로,  공급자를 읽기 전용 공급자와 업데이트 가능 공급자로 분류하면 편리합니다.  
  
-   Visual C\+\+ 6.0은 읽기 전용 공급자만 지원합니다.  [OLE DB 공급자 만들기](../../data/oledb/creating-an-ole-db-provider.md)에서는 읽기 전용 공급자를 만드는 방법에 대해 설명합니다.  
  
-   Visual C\+\+ .NET은 데이터 저장소를 업데이트할 수 있는, 즉 데이터 저장소에 쓸 수 있는 업데이트 가능 공급자를 지원합니다.  업데이트 가능 공급자에 대한 자세한 내용은 [업데이트 가능 공급자 만들기](../../data/oledb/creating-an-updatable-provider.md)를 참조하십시오. [UpdatePV](http://msdn.microsoft.com/ko-kr/c8bed873-223c-4a7d-af55-f90138c6f38f) 샘플은 업데이트 가능 공급자의 예제입니다.  
  
 자세한 내용은 다음을 참조하십시오.  
  
-   [OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)  
  
-   [OLE DB 공급자 만들기](../../data/oledb/creating-an-ole-db-provider.md)  
  
-   [OLE DB 프로그래밍](../../data/oledb/ole-db-programming.md)  
  
## 참고 항목  
 [데이터 액세스](../Topic/Data%20Access%20in%20Visual%20C++.md)   
 [OLE DB SDK 설명서](https://msdn.microsoft.com/en-us/library/ms722784.aspx)   
 [OLE DB 프로그래머 참조](https://msdn.microsoft.com/en-us/library/ms713643.aspx)