---
title: 클래스 (아키텍처) 보기 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.view
dev_langs:
- C++
helpviewer_keywords:
- form and record views [MFC]
- view classes [MFC]
- control views [MFC]
- view classes [MFC], architecture
ms.assetid: 8894579a-1436-441e-b985-83711061e495
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 11bb3d9e551089a156d255f7b27fb55cbe87bdbe
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="view-classes-architecture"></a>뷰 클래스(아키텍처)
`CView` 및 그 파생된 클래스는 프레임 창의 클라이언트 영역을 나타내는 자식 창. 뷰는 데이터를 표시 및 문서에 대 한 입력을 허용 합니다.  
  
 뷰 클래스 문서 클래스 및 문서 템플릿 개체를 사용 하 여 프레임 창 클래스와 관련이 있습니다.  
  
 [CView](../mfc/reference/cview-class.md)  
 문서 데이터의 응용 프로그램 관련 보기에 대 한 기본 클래스입니다. 뷰는 데이터를 표시 및 편집 하거나 데이터를 선택 하려면 사용자 입력을 허용 합니다. 사용자 보기 클래스를 파생 `CView`합니다.  
  
 [CScrollView](../mfc/reference/cscrollview-class.md)  
 스크롤 기능이 뷰에 대 한 기본 클래스입니다. 뷰 클래스를 파생 `CScrollView` 자동 스크롤할 수 있도록 합니다.  
  
## <a name="form-and-record-views"></a>폼 및 레코드 뷰  
 폼 뷰 뷰 스크롤도 됩니다. 대화 상자 템플릿에 기반 합니다.  
  
 레코드 뷰는 폼 보기에서 파생 됩니다. 대화 상자 템플릿 외에 갖게 데이터베이스에 연결 됩니다.  
  
 [CFormView](../mfc/reference/cformview-class.md)  
 레이아웃에 대화 상자 템플릿을 정의 하는 스크롤 보기입니다. 클래스를 파생 `CFormView` 대화 상자 템플릿을 기반으로 사용자 인터페이스를 구현 합니다.  
  
 [CDaoRecordView](../mfc/reference/cdaorecordview-class.md)  
 폼을 제공 보기 개체 DAO (Data Access) 레코드 집합 개체에 직접 연결 합니다. 모든 폼 보기와 같은 한 `CDaoRecordView` 대화 상자 템플릿을 기반으로 합니다.  
  
 [CHtmlView](../mfc/reference/chtmlview-class.md)  
 웹 응용 프로그램 내에서 검색에 대 한 컨트롤을 지원 합니다. 컨트롤은 MFC에 동적 HTML을 지원합니다.  
  
 [COLEDBRecordView](../mfc/reference/coledbrecordview-class.md)  
 폼 보기에 대 한 MFC OLE DB 지원을 제공합니다.  
  
 [CRecordView](../mfc/reference/crecordview-class.md)  
 폼을 제공 ODBC Open Database Connectivity () 레코드 집합 개체에 직접 연결 된입니다. 모든 폼 보기와 같은 한 `CRecordView` 대화 상자 템플릿을 기반으로 합니다.  
  
## <a name="control-views"></a>컨트롤 뷰  
 뷰 컨트롤의 보기도 컨트롤을 표시합니다.  
  
 [CCtrlView](../mfc/reference/cctrlview-class.md)  
 Windows 컨트롤과 관련 된 모든 보기에 대 한 기본 클래스입니다. 컨트롤에 따라 보기에 대 한 설명은 다음과 같습니다.  
  
 [CEditView](../mfc/reference/ceditview-class.md)  
 Windows 표준에 포함 된 보기 편집 컨트롤 (참조 [CEdit](../mfc/reference/cedit-class.md)). 지원 텍스트 편집 컨트롤, 검색, 교체 및 스크롤 기능을 편집 합니다.  
  
 [CRichEditView](../mfc/reference/cricheditview-class.md)  
 풍부한 Windows를 포함 하는 뷰 편집 컨트롤 (참조 [CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)). 편집 컨트롤의 기능 외에 서식 있는 편집 컨트롤 지원 글꼴, 색, 단락 서식 지정 및 포함 된 OLE 개체입니다.  
  
 [CListView](../mfc/reference/clistview-class.md)  
 Windows 목록 컨트롤을 포함 하는 뷰 (참조 [CListCtrl](../mfc/reference/clistctrl-class.md)). 목록 컨트롤 아이콘 및 문자열 파일 탐색기의 오른쪽 창에 비슷한 방식으로 표시합니다.  
  
 [CTreeView](../mfc/reference/ctreeview-class.md)  
 Windows 트리 컨트롤을 포함 하는 뷰 (참조 [CTreeCtrl](../mfc/reference/ctreectrl-class.md)). 트리 컨트롤 아이콘 및 파일 탐색기의 왼쪽된 창에 비슷한 방식으로 계층으로 정렬 하는 문자열을 표시 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스 개요](../mfc/class-library-overview.md)

