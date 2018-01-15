---
title: "클래스 (Windows) 보기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.classes.view
dev_langs: C++
helpviewer_keywords:
- form and record views [MFC]
- splitter window classes [MFC]
- view classes [MFC], Windows
ms.assetid: b11683fb-9f43-4de3-9499-2b55775f9870
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3d737176df2676f543f47bb77a0d205fa7c908fc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="view-classes-windows"></a>뷰 클래스(Windows)
`CView`및 그 파생된 클래스는 프레임 창의 클라이언트 영역을 나타내는 자식 창. 뷰는 데이터를 표시 및 문서에 대 한 입력을 허용 합니다.  
  
 뷰 클래스 문서 클래스 및 문서 템플릿 개체를 사용 하 여 프레임 창 클래스와 관련이 있습니다.  
  
 [CView](../mfc/reference/cview-class.md)  
 문서 데이터의 응용 프로그램 관련 보기에 대 한 기본 클래스입니다. 뷰는 데이터를 표시 및 편집 하거나 데이터를 선택 하려면 사용자 입력을 허용 합니다. 뷰 클래스 또는 클래스에서 파생 `CView`합니다.  
  
 [CScrollView](../mfc/reference/cscrollview-class.md)  
 스크롤 기능이 뷰에 대 한 기본 클래스입니다. 뷰 클래스를 파생 `CScrollView` 자동 스크롤할 수 있도록 합니다.  
  
## <a name="form-and-record-views"></a>폼 및 레코드 뷰  
 폼 뷰 뷰 스크롤도 됩니다. 대화 상자 템플릿에 기반 합니다.  
  
 레코드 뷰는 폼 보기에서 파생 됩니다. 대화 상자 템플릿 외에 갖게 데이터베이스에 연결 됩니다.  
  
 [CFormView](../mfc/reference/cformview-class.md)  
 레이아웃에 대화 상자 템플릿을 정의 하는 스크롤 보기입니다. 클래스를 파생 `CFormView` 대화 상자 템플릿을 기반으로 사용자 인터페이스를 구현 합니다.  
  
 [CDaoRecordView](../mfc/reference/cdaorecordview-class.md)  
 폼을 제공 보기 개체 DAO (Data Access) 레코드 집합 개체에 직접 연결 합니다. 모든 폼 보기와 같은 한 `CDaoRecordView` 대화 상자 템플릿을 기반으로 합니다.  
  
 [CRecordView](../mfc/reference/crecordview-class.md)  
 폼을 제공 ODBC Open Database Connectivity () 레코드 집합 개체에 직접 연결 된입니다. 모든 폼 보기와 같은 한 `CRecordView` 대화 상자 템플릿을 기반으로 합니다.  
  
 [CHtmlEditView](../mfc/reference/chtmleditview-class.md)  
 HTML WebBrowser 편집 플랫폼의 기능을 제공 하는 폼 보기입니다.  
  
## <a name="control-views"></a>컨트롤 뷰  
 뷰 컨트롤의 보기도 컨트롤을 표시합니다.  
  
 [CCtrlView](../mfc/reference/cctrlview-class.md)  
 Windows 컨트롤과 관련 된 모든 보기에 대 한 기본 클래스입니다. 컨트롤에 따라 보기에 대 한 설명은 다음과 같습니다.  
  
 [CEditView](../mfc/reference/ceditview-class.md)  
 Windows 표준에 포함 된 보기 편집 컨트롤 (참조 [CEdit](../mfc/reference/cedit-class.md)). 지원 텍스트 편집 컨트롤, 검색, 교체 및 스크롤 기능을 편집 합니다.  
  
 [CRichEditView](../mfc/reference/cricheditview-class.md)  
 풍부한 Windows를 포함 하는 뷰 편집 컨트롤 (참조 [CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)). 편집 컨트롤의 기능 외에 서식 있는 편집 컨트롤 지원 글꼴, 색, 단락 서식 지정 및 포함 된 OLE 개체입니다.  
  
 [CListView](../mfc/reference/clistview-class.md)  
 Windows 목록 컨트롤을 포함 하는 뷰 (참조 [CListCtrl](../mfc/reference/clistctrl-class.md)). 목록 컨트롤 아이콘 및 레이블 파일 탐색기의 오른쪽 창에 비슷한 방식으로 구성 된 각 항목의 컬렉션을 표시 합니다.  
  
 [CTreeView](../mfc/reference/ctreeview-class.md)  
 Windows 트리 컨트롤을 포함 하는 뷰 (참조 [CTreeCtrl](../mfc/reference/ctreectrl-class.md)). 트리 컨트롤에 아이콘과 레이블을 파일 탐색기의 왼쪽된 창에 비슷한 방식으로 정렬의 계층 목록을 표시 합니다.  
  
## <a name="related-classes"></a>관련된 클래스  
 `CSplitterWnd`단일 한 프레임 창 내에서 여러 뷰를 포함할 수 있습니다. `CPrintDialog`및 `CPrintInfo` 뷰의 인쇄 및 인쇄 미리 보기 기능을 지원 합니다. `CRichEditDoc`및 `CRichEditCntrItem` 와 함께 사용 됩니다 `CRichEditView` OLE 컨테이너 기능을 구현 하 합니다.  
  
 [CSplitterWnd](../mfc/reference/csplitterwnd-class.md)  
 사용자를 여러 개의 창으로 분할할 수 있는 창입니다. 이러한 창이 고 사용자 또는 고정된 크기가 크기 조정할 수 있습니다.  
  
 [CPrintDialog](../mfc/reference/cprintdialog-class.md)  
 파일 인쇄를 위한 표준 대화 상자를 제공 합니다.  
  
 [CPrintInfo](../mfc/reference/cprintinfo-structure.md)  
 인쇄 또는 인쇄 미리 보기 작업에 대 한 정보를 포함 하는 구조입니다. 사용 하는 `CView`의 아키텍처를 인쇄 합니다.  
  
 [CRichEditDoc](../mfc/reference/cricheditdoc-class.md)  
 에 있는 OLE 클라이언트 항목의 목록을 유지 관리는 `CRichEditView`합니다.  
  
 [CRichEditCntrItem](../mfc/reference/cricheditcntritem-class.md)  
 항목에 저장 하는 OLE에 클라이언트 액세스를 제공는 `CRichEditView`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스 개요](../mfc/class-library-overview.md)

