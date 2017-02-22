---
title: "ATL 데이터베이스 클래스(OLE DB 템플릿) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "데이터베이스 클래스[C++], ATL"
  - "데이터베이스 클래스[C++], OLE DB"
  - "OLE DB 템플릿[C++], ATL 데이터베이스 클래스"
ms.assetid: 219766aa-e18a-405f-9e36-d7a0fdb31b2b
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# ATL 데이터베이스 클래스(OLE DB 템플릿)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

동일한 방식을 사용하여 다양한 정보 소스 및 형식으로 구성된 데이터에 액세스할 수 있도록 하는 COM 인터페이스 집합인 OLE DB는 여러 가지 방법을 사용하여 구현할 수 있습니다.  
  
 OLE DB 템플릿은 ATL에 포함된 C\+\+ 템플릿으로서, 자주 사용되는 여러 가지 OLE DB 인터페이스를 구현하는 클래스를 제공하여 성능이 뛰어난 OLE DB 데이터베이스 기술을 보다 쉽게 사용할 수 있도록 합니다.  
  
 이 템플릿 라이브러리에는 다음 두 부분이 포함되어 있습니다.  
  
-   [OLE DB 소비자 템플릿](../data/oledb/ole-db-consumer-templates-cpp.md) OLE DB 클라이언트\(소비자\) 응용 프로그램을 구현하는 데 사용합니다.  
  
-   [OLE DB 공급자 템플릿](../data/oledb/ole-db-provider-templates-cpp.md) OLE DB 서버\(공급자\) 응용 프로그램을 구현하는 데 사용합니다.  
  
 이외에도, OLE DB 소비자를 쉽게 만들 수 있는 [OLE DB Consumer Attributes](../windows/ole-db-consumer-attributes.md)이 포함되어 있습니다.  OLE DB 특성은 OLE DB 소비자 템플릿에 기반한 코드를 삽입하여 사용 가능한 OLE DB 소비자를 만듭니다.  
  
 MFC 라이브러리에는 컨트롤의 데이터베이스 레코드를 표시하는 클래스, 즉 [COleDBRecordView](../mfc/reference/coledbrecordview-class.md)가 포함되어 있습니다.  보기는 `CRowset` 개체에 직접 연결된 폼 보기이며, 대화 상자 템플릿의 컨트롤에 `CRowset` 개체의 필드를 표시합니다.  
  
 For more information, see [OLE DB Programming](../data/oledb/ole-db-programming.md) and [OLE DB Programmer's Guide](http://go.microsoft.com/fwlink/?LinkId=121548).  
  
## 참고 항목  
 [OLE DB 소비자 만들기](../data/oledb/creating-an-ole-db-consumer.md)   
 [OLE DB 공급자 만들기](../data/oledb/creating-an-ole-db-provider.md)   
 [OLE DB 소비자 템플릿 참조](../data/oledb/ole-db-consumer-templates-reference.md)   
 [OLE DB 공급자 템플릿 참조](../data/oledb/ole-db-provider-templates-reference.md)   
 [OLE DB Templates Samples](http://msdn.microsoft.com/ko-kr/08958863-0b5f-41ad-ae99-fca7440c553c)