---
title: "OLE DB 레코드 뷰를 사용 하 여 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- OLE DB record views
- COleDBRecordView class, overview
- rowsets, record views
- record views, record view objects
- OLE DB, record views
- MFC, record views
ms.assetid: 1cd3e595-ce08-43d8-a0a9-d03b5d3e24ce
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c4e57f320c8b207e7b1c8721ab25744cd1f128bc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="using-ole-db-record-views"></a>OLE DB 레코드 뷰 사용
MFC 응용 프로그램에서 OLE DB 행 집합 데이터를 표시 하려는 경우에 MFC 클래스 사용 해야 [COleDBRecordView](../../mfc/reference/coledbrecordview-class.md)합니다. 레코드 뷰 개체에서 만든 `COleDBRecordView` MFC 컨트롤에 데이터베이스 레코드를 표시할 수 있습니다. 레코드 뷰는 직접 만든 OLE DB 행 집합 개체에 연결 대화 상자 폼 보기의 `CRowset` 템플릿 클래스입니다. 행 집합 개체에 대 한 핸들을 가져오는 것은 간단 합니다.  
  
```  
COleDBRecordView myRecordView;  
...  
// CProductAccessor is a user record class  
CRowset<CAccessor<CProductAccessor>> myRowSet = myRecordView.OnGetRowset();  
```  
  
 필드를 표시 하는 보기는 `CRowset` 대화 상자의 컨트롤에는 개체입니다. `COleDBRecordView` 대화 상자 데이터 교환 (DDX)을 사용 하 여 개체 및 탐색 기능에 기본 제공 `CRowset` (**MoveFirst**, `MoveNext`, `MovePrev`, 및 `MoveLast`) 데이터의 이동 자동화 하려면 행 집합의 필드와 폼의 컨트롤 간의. `COleDBRecordView`추적 행 집합에서 사용자의 위치 레코드 뷰 사용자 인터페이스를 제공 업데이트할 수 있도록는 [OnMove](../../mfc/reference/coledbrecordview-class.md#onmove) 메서드 간에 이동 하기 전에 현재 레코드를 업데이트 합니다.  
  
 DDX 함수를 사용할 수 있습니다 **COleDbRecordView** 데이터베이스 레코드 집합에서 직접 데이터를 가져오고 대화 상자 컨트롤에 표시를 합니다. 사용 해야는 **DDX_\***  메서드 (같은 `DDX_Text`)이 아니라는 **DDX_Field\***  함수 (같은 `DDX_FieldText`)와 **COleDbRecordView** .  
  
## <a name="see-also"></a>참고 항목  
 [접근자 사용](../../data/oledb/using-accessors.md)   
 [COleDBRecordView 클래스](../../mfc/reference/coledbrecordview-class.md)