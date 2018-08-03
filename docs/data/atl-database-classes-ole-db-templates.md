---
title: ATL 데이터베이스 클래스 (OLE DB 템플릿) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- OLE DB templates [C++], ATL database classes
- database classes [C++], OLE DB
- database classes [C++], ATL
ms.assetid: 219766aa-e18a-405f-9e36-d7a0fdb31b2b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 083ac7485ce2056ab97ca32142be3e88094573f9
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2018
ms.locfileid: "39337887"
---
# <a name="atl-database-classes-ole-db-templates"></a>ATL 데이터베이스 클래스(OLE DB 템플릿)
Microsoft OLE DB 데이터를 다양 한 소스 및 형식에 대 한 균일 한 액세스를 제공 하는 COM 인터페이스 집합의 몇 가지 구현을 제공 합니다.  OLE DB는 공식적으로 사용 되지 않습니다. 이 설명서는 레거시 코드를 유지 하는 개발자입니다. 새 응용 프로그램은 SQL 데이터 원본에 연결할 ODBC를 사용 해야 합니다.
  
 OLE DB 템플릿 템플릿은 c + + ATL에서 OLE DB 데이터베이스 기술을 쉽게 여러 가지 자주 사용 되는 OLE DB 인터페이스를 구현 하는 클래스를 제공 하 여 사용할 수 있도록 합니다.  
  
 이 템플릿 라이브러리 포함 두 부분으로 구성이 되어 있습니다.  
  
-   [OLE DB 소비자 템플릿](../data/oledb/ole-db-consumer-templates-cpp.md) OLE DB (소비자) 클라이언트 응용 프로그램을 구현 하는 데 사용 합니다.  
  
-   [OLE DB 공급자 템플릿](../data/oledb/ole-db-provider-templates-cpp.md) OLE DB 서버 (공급자) 응용 프로그램을 구현 하는 데 사용 합니다.  
  
 또한 합니다 [OLE DB 소비자 특성](../windows/ole-db-consumer-attributes.md) OLE DB 소비자를 만드는 편리한 방법을 제공 합니다. OLE DB 작업 OLE DB 소비자를 만드는 OLE DB 소비자 템플릿을 기반으로 하는 코드를 삽입 합니다.  
  
 MFC 라이브러리 클래스를 포함 하는 참고 [COleDBRecordView](../mfc/reference/coledbrecordview-class.md), 컨트롤의 데이터베이스 레코드를 표시 하는 합니다. 뷰는에 직접 연결 하는 폼 보기를 `CRowset` 개체 및 필드가 표시 됩니다는 `CRowset` 대화 상자 템플릿의 컨트롤에는 개체입니다.  
  
 자세한 내용은 [OLE DB 프로그래밍](../data/oledb/ole-db-programming.md) 하 고 [OLE DB Programmer's Guide](http://go.microsoft.com/fwlink/p/?linkid=121548)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 소비자 만들기](../data/oledb/creating-an-ole-db-consumer.md)   
 [OLE DB 공급자 만들기](../data/oledb/creating-an-ole-db-provider.md)   
 [OLE DB 소비자 템플릿 참조](../data/oledb/ole-db-consumer-templates-reference.md)   
 [OLE DB 공급자 템플릿 참조](../data/oledb/ole-db-provider-templates-reference.md)   
 [OLE DB 템플릿 샘플](http://msdn.microsoft.com/08958863-0b5f-41ad-ae99-fca7440c553c)