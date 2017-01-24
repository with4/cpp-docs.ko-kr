---
title: "명령 및 테이블 | Microsoft Docs"
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
  - "CAccessorRowset 클래스, 명령 및 테이블 클래스"
  - "CCommand 클래스, OLE DB 소비자 템플릿"
  - "명령[C++], OLE DB 소비자 템플릿"
  - "CTable 클래스"
  - "OLE DB 소비자 템플릿, 명령 지원"
  - "OLE DB 소비자 템플릿, 테이블 지원"
  - "행 집합, 액세스"
  - "테이블[C++], OLE DB 소비자 템플릿"
ms.assetid: 4bd3787b-6d26-40a9-be0c-083080537c12
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 명령 및 테이블
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

명령과 테이블을 사용하면 행 집합에 액세스할 수 있습니다. 즉, 행 집합을 열거나 명령을 실행하거나 열을 바인딩할 수 있습니다.  [CCommand](../../data/oledb/ccommand-class.md) 및 [CTable](../../data/oledb/ctable-class.md) 클래스는 명령과 테이블 개체를 각각 인스턴스화합니다.  이들 클래스는 다음 그림에서 볼 수 있듯이 [CAccessorRowset](../../data/oledb/caccessorrowset-class.md)에서 파생됩니다.  
  
 ![CCommand 및 CTable](../../data/oledb/media/vccommandstables.gif "vcCommandsTables")  
명령 및 테이블 클래스  
  
 앞의 테이블에서 `TAccessor`는 [접근자 형식](../../data/oledb/accessors-and-rowsets.md)에 나열된 모든 접근자 형식이 가능합니다.  TRowset은 [행 집합 형식](../../data/oledb/accessors-and-rowsets.md)의 모든 행 집합 형식이 가능합니다.  TMultiple은 결과 형식\(단일 또는 여러 결과 집합\)을 지정합니다.  
  
 [ATL OLE DB 소비자 마법사](../../atl/reference/atl-ole-db-consumer-wizard.md)를 사용하면 명령 개체를 원하는지 아니면 테이블 개체를 원하는지의 여부를 지정할 수 있습니다.  
  
-   명령이 없는 데이터 소스에는 `CTable` 클래스를 사용할 수 있습니다.  일반적으로 이 클래스는 매개 변수를 지정하지 않고 여러 결과가 필요 없는 단순 행 집합에 사용됩니다.  이러한 단순 클래스는 사용자가 지정한 테이블 이름을 사용하여 데이터 소스에서 테이블을 엽니다.  
  
-   명령을 지원하는 데이터 소스에는 대신 `CCommand` 클래스를 사용할 수 있습니다.  명령을 실행하려면 이 클래스에서 [Open](../../data/oledb/ccommand-open.md)을 호출합니다.  다른 방법으로는 `Prepare`를 호출하여 두 번 이상 실행할 명령을 준비할 수 있습니다.  
  
     **CCommand** 에는 접근자 형식, 행 집합 형식 및 결과 형식\(`CNoMultipleResults`\(기본값\) 또는  `CMultipleResults`\)이라는 세 가지 템플릿 인수가 있습니다.  `CMultipleResults`를 지정하는 경우 `CCommand` 클래스는 **IMultipleResults** 인터페이스를 지원하고 여러 행 집합을 처리합니다.  [DBViewer](http://msdn.microsoft.com/ko-kr/07620f99-c347-4d09-9ebc-2459e8049832) 샘플에서 여러 결과를 처리하는 방법을 보여 줍니다.  
  
## 참고 항목  
 [OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)