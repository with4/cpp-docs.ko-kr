---
title: "기록 보기 (데이터 액세스) | Microsoft Docs"
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
- MFC [C++], record views
- ODBC recordsets [C++], record views
- databases [C++], record views
- record views [C++]
- forms [C++], data access tasks
ms.assetid: 562122d9-01d8-4284-acf6-ea109ab0408d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e698cad29405fce4b5a0d23e166217502753dc1d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="record-views--mfc-data-access"></a>레코드 뷰  (MFC Data Access)
이 섹션은 MFC ODBC 클래스에만 적용 됩니다. OLE DB 레코드 뷰에 대 한 정보를 참조 하십시오. [COleDBRecordView](../mfc/reference/coledbrecordview-class.md) 및 [를 사용 하 여 OLE DB 레코드 뷰](../data/oledb/using-ole-db-record-views.md)합니다.  
  
 양식 기반 데이터 액세스 응용 프로그램을 지원 하려면 클래스 라이브러리는 클래스를 제공 [CRecordView](../mfc/reference/crecordview-class.md)합니다. 레코드 뷰는 해당 컨트롤의 필드 데이터 멤버에 직접 매핑되는 폼 뷰 개체는 [레코드 집합](../data/odbc/recordset-odbc.md) 개체 (및 데이터 원본에 테이블 또는 쿼리 결과의 해당 열에 간접적으로). 해당 기본 클래스와 마찬가지로 [CFormView](../mfc/reference/cformview-class.md), `CRecordView` 대화 상자 템플릿 리소스를 기반으로 합니다.  
  
## <a name="form-uses"></a>폼 사용  
 폼은 다음과 같은 여러 데이터 액세스 작업에 유용합니다.  
  
-   데이터 입력  
  
-   데이터의 읽기 전용 검사 수행  
  
-   데이터 업데이트  
  
## <a name="further-reading-about-record-views"></a>레코드 뷰에 대한 추가 자료  
 아래 항목의 자료는 ODBC 기반 및 DAO 기반 클래스 둘 다에 적용됩니다. ODBC의 경우 `CRecordView`를 사용하고 DAO의 경우에는 `CDaoRecordView`를 사용합니다.  
  
 다음과 같은 내용을 다룹니다.  
  
-   [레코드 뷰 클래스의 기능](../data/features-of-record-view-classes-mfc-data-access.md)  
  
-   [레코드 뷰의 데이터 교환](../data/data-exchange-for-record-views-mfc-data-access.md)  
  
-   [레코드 뷰 작업에서 역할](../data/your-role-in-working-with-a-record-view-mfc-data-access.md)  
  
-   [레코드 뷰 디자인 및 만들기](../data/designing-and-creating-a-record-view-mfc-data-access.md)  
  
-   [레코드 뷰 사용](../data/using-a-record-view-mfc-data-access.md)  
  
## <a name="see-also"></a>참고 항목  
 [데이터 액세스 프로그래밍 (MFC/ATL)](../data/data-access-programming-mfc-atl.md)   
 [ODBC 드라이버 목록](../data/odbc/odbc-driver-list.md)