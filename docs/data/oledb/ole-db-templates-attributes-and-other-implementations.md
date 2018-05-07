---
title: OLE DB 템플릿, 특성 및 기타 구현 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB, implementations
- OLE DB templates, about OLE DB templates
- OLE DB templates
ms.assetid: 0c780c1b-9bba-4788-8c33-8552d9f120ac
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ef9baf43ded1533eb7f4962db7344f9dc1def0ce
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="ole-db-templates-attributes-and-other-implementations"></a>OLE DB 템플릿, 특성 및 기타 구현
## <a name="atl-ole-db-templates"></a>ATL OLE DB 템플릿  
 OLE DB 템플릿, ATL (액티브 템플릿 라이브러리)의 일부인 고성능 OLE DB 데이터베이스 기술 여러 가지 자주 사용 되는 OLE DB 인터페이스를 구현 하는 클래스를 제공 하 여 사용 하기 쉽도록 합니다. 라이브러리는이 템플릿과 함께 OLE DB 시작 응용 프로그램을 만들기 위한 마법사 지원을 제공 됩니다.  
  
 이 템플릿 라이브러리에는 두 부분이 포함 됩니다.  
  
-   **OLE DB 소비자 템플릿** OLE DB (소비자) 클라이언트 응용 프로그램을 구현 하는 데 사용 합니다.  
  
-   **OLE DB 공급자 템플릿** OLE DB 서버 (공급자) 응용 프로그램을 구현 하는 데 사용 합니다.  
  
 OLE DB 템플릿을 사용하려면 C++ 템플릿, COM 및 OLE DB 인터페이스에 대해 잘 알고 있어야 합니다. OLE DB에 익숙하지 않은 경우 참조 [OLE DB Programmer's Reference](https://msdn.microsoft.com/en-us/library/ms713643.aspx)합니다.  
  
 자세한 내용은 다음을 수행할 수 있습니다.  
  
-   에 대 한 항목을 읽어는 [OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md) 또는 [OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)합니다.  
  
-   만들기는 [OLE DB 소비자](../../data/oledb/creating-an-ole-db-consumer.md) 또는 [OLE DB 공급자](../../data/oledb/creating-an-ole-db-provider.md)합니다.  
  
-   목록을 보려면 [OLE DB 소비자 클래스](../../data/oledb/ole-db-consumer-templates-reference.md) 또는 [OLE DB 공급자 클래스](../../data/oledb/ole-db-provider-templates-reference.md)합니다.  
  
-   목록을 보려면 [OLE DB 템플릿 샘플](http://msdn.microsoft.com/en-us/08958863-0b5f-41ad-ae99-fca7440c553c)합니다.  
  
-   참조 [OLE DB Programmer's Reference](https://msdn.microsoft.com/en-us/library/ms713643.aspx) (Windows SDK)에 있습니다.  
  
## <a name="ole-db-attributes"></a>OLE DB 특성  
 [OLE DB 소비자 특성](../../windows/ole-db-consumer-attributes.md) OLE DB 소비자를 만들지는 편리한 방법을 제공 합니다. OLE DB 특성에 따라 코드를 삽입는 [OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-reference.md) 작업 OLE DB 소비자 및 공급자를 만들려고 합니다. 특성에서 지원 되지 않습니다는 기능을 지정 해야 할 경우 코드에서 OLE DB 템플릿 특성과 함께에서 사용할 수 있습니다.  
  
## <a name="mfc-ole-db-classes"></a>MFC OLE DB 클래스  
 MFC 라이브러리에 클래스를 [COleDBRecordView](../../mfc/reference/coledbrecordview-class.md), 컨트롤에 데이터베이스 레코드를 표시 하는 합니다. 뷰는에 직접 연결 하는 폼 보기는 `CRowset` 개체 및 필드가 표시 됩니다는 `CRowset` 대화 상자 템플릿에 컨트롤의 개체입니다. 이동에 대 한 기본 구현을 제공 하는 첫 번째 다음, 이전 또는 마지막 레코드 및 보기에 현재 레코드를 업데이트 하기 위한 인터페이스입니다. 자세한 내용은 `COleDBRecordView`을 참조하세요.  
  
## <a name="ole-db-sdk-interfaces"></a>OLE DB SDK 인터페이스  
 OLE DB 템플릿 OLE DB 기능 지원 하지 않는 경우에는 OLE DB 인터페이스를 직접 사용 해야 합니다. 자세한 내용은 참조 [OLE DB Programmer's Reference](https://msdn.microsoft.com/en-us/library/ms713643.aspx) Windows sdk에서입니다.  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 프로그래밍](../../data/oledb/ole-db-programming.md)   
 [OLE DB 프로그래밍 개요](../../data/oledb/ole-db-programming-overview.md)