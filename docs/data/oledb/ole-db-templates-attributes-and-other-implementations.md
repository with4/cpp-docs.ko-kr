---
title: "OLE DB 템플릿, 특성 및 기타 구현 | Microsoft Docs"
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
  - "OLE DB 템플릿"
  - "OLE DB 템플릿, OLE DB 템플릿 정보"
  - "OLE DB, 구현"
ms.assetid: 0c780c1b-9bba-4788-8c33-8552d9f120ac
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# OLE DB 템플릿, 특성 및 기타 구현
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## ATL OLE DB 템플릿  
 ATL \(Active Template Library\)의 일부분인 OLE DB 템플릿은 일반적으로 사용되는 여러 OLE DB 인터페이스를 구현하는 클래스를 제공하는 방법으로 고성능 OLE DB 데이터베이스 기술을 사용하기 쉽게 만들어 줍니다.  OLE DB 시작 응용 프로그램을 만드는 작업에는 이 템플릿 라이브러리에 더불어 마법사가 지원됩니다.  
  
 이 템플릿 라이브러리에는 다음 두 부분이 포함되어 있습니다.  
  
-   **OLE DB 소비자 템플릿** OLE DB 클라이언트\(소비자\) 응용 프로그램을 구현하는 데 사용합니다.  
  
-   **OLE DB 공급자 템플릿** OLE DB 서버\(공급자\) 응용 프로그램을 구현하는 데 사용합니다.  
  
 OLE DB 템플릿을 사용하기 위해서는 C\+\+ 템플릿, COM 및 OLE DB 인터페이스에 대해 잘 알고 있어야 합니다.  OLE DB에 익숙하지 않은 경우에는 [OLE DB Programmer's Reference](https://msdn.microsoft.com/en-us/library/ms713643.aspx)를 참조하십시오.  
  
 자세한 내용을 얻기 위해 다음과 같이 할 수 있습니다.  
  
-   [OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md) 또는 [OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)의 항목을 참조합니다.  
  
-   [OLE DB 소비자](../../data/oledb/creating-an-ole-db-consumer.md) 또는 [OLE DB 공급자](../../data/oledb/creating-an-ole-db-provider.md)를 만듭니다.  
  
-   [OLE DB Consumer 클래스](../../data/oledb/ole-db-consumer-templates-reference.md) 또는 [OLE DB Provider 클래스](../../data/oledb/ole-db-provider-templates-reference.md)의 목록을 봅니다.  
  
-   [OLE DB 템플릿 샘플](http://msdn.microsoft.com/ko-kr/08958863-0b5f-41ad-ae99-fca7440c553c)의 목록을 봅니다.  
  
-   [!INCLUDE[winsdkshort](../../atl/reference/includes/winsdkshort_md.md)]에 있는 [OLE DB Programmer's Reference](https://msdn.microsoft.com/en-us/library/ms713643.aspx)를 참조하십시오.  
  
## OLE DB 특성  
 [OLE DB Consumer Attributes](../../windows/ole-db-consumer-attributes.md)는 OLE DB 소비자를 만드는 편리한 방법을 제공합니다.  OLE DB 특성은 작업 중인 OLE DB 소비자와 공급자를 만들기 위해 [OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-reference.md)를 기반으로 하는 코드를 삽입합니다.  특성에서 지원하지 않는 기능을 지정해야 하는 경우, 코드에서 OLE DB 템플릿을 특성과 결합하여 사용할 수 있습니다.  
  
## MFC OLE DB 클래스  
 MFC 라이브러리는 컨트롤에 데이터베이스 기록을 표시하는 클래스 [COleDBRecordView](../../mfc/reference/coledbrecordview-class.md)를 가지고 있습니다.  보기는 `CRowset` 개체에 직접 연결된 폼 보기이며, 대화 상자 템플릿의 컨트롤에 `CRowset` 개체의 필드를 표시합니다.  또한 보기는 첫번째, 다음, 이전 또는 마지막 기록으로 이동하는 기본 구현 및 보기의 현재 기록을 업데이트하는 인터페이스를 제공합니다.  자세한 내용은 `COleDBRecordView`을 참조하십시오.  
  
## OLE DB SDK 인터페이스  
 OLE DB 템플릿이 OLE DB 기능을 지원하지 않는 경우, OLE DB 인터페이스 자체를 사용해야 합니다.  자세한 내용은 [!INCLUDE[winsdkshort](../../atl/reference/includes/winsdkshort_md.md)]에 있는 [OLE DB Programmer's Reference](https://msdn.microsoft.com/en-us/library/ms713643.aspx)를 참조하십시오.  
  
## 참고 항목  
 [OLE DB 프로그래밍](../../data/oledb/ole-db-programming.md)   
 [OLE DB 프로그래밍 개요](../../data/oledb/ole-db-programming-overview.md)