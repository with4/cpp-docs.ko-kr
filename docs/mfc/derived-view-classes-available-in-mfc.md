---
title: MFC에서 사용할 수 있는 뷰 클래스를 파생 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CView class [MFC], classes derived from
- classes [MFC], derived
- derived classes [MFC], view classes
- view classes [MFC], derived
ms.assetid: dba42178-7459-4ccc-b025-f3d9b8a4b737
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7b166e64c57482586e145cecc9e79317eea282b5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33345666"
---
# <a name="derived-view-classes-available-in-mfc"></a>MFC에서 사용할 수 있는 파생된 뷰 클래스
다음 표에서 MFC의 뷰 클래스 및 형식 간의 관계를 보여 줍니다. 뷰 클래스의 기능 파생 되는 MFC 뷰 클래스에 따라 다릅니다.  
  
### <a name="view-classes"></a>뷰 클래스  
  
|클래스|설명|  
|-----------|-----------------|  
|[CView](../mfc/reference/cview-class.md)|모든 보기의 기본 클래스입니다.|  
|[CCtrlView](../mfc/reference/cctrlview-class.md)|기본 클래스의 `CTreeView`, `CListView`, `CEditView`, 및 `CRichEditView`합니다. 이러한 클래스에는 문서/뷰 아키텍처를 사용 하 여 표시 된 Windows 공용 컨트롤 수 있습니다.|  
|[CEditView](../mfc/reference/ceditview-class.md)|Windows 기반으로 하는 간단한 뷰 상자 컨트롤을 편집 합니다. 입력 및 텍스트 편집을 허용 하 고 간단한 텍스트 편집기 응용 프로그램에 대 한 기준으로 사용할 수 있습니다. `CRichEditView`을 참조하십시오.|  
|[CRichEditView](../mfc/reference/cricheditview-class.md)|포함 하는 보기는 [CRichEditCtrl](../mfc/reference/cricheditctrl-class.md) 개체입니다. 이 클래스는 유사 `CEditView`, 달리 하지만 `CEditView`, `CRichEditView` 핸들 서식 있는 텍스트입니다.|  
|[CListView](../mfc/reference/clistview-class.md)|포함 하는 보기는 [CListCtrl](../mfc/reference/clistctrl-class.md) 개체입니다.|  
|[CTreeView](../mfc/reference/ctreeview-class.md)|포함 하는 보기는 [CTreeCtrl](../mfc/reference/ctreectrl-class.md) Visual c + +의 솔루션 탐색기 창 유사한 보기에 대 한 개체입니다.|  
|[CScrollView](../mfc/reference/cscrollview-class.md)|기본 클래스의 `CFormView`, `CRecordView`, 및 `CDaoRecordView`합니다. 보기의 내용을 스크롤 기능을 구현 합니다.|  
|[CFormView](../mfc/reference/cformview-class.md)|폼 보기, 컨트롤을 포함 하는 뷰입니다. 폼 기반 응용 프로그램 하나 이상의 폼 인터페이스를 제공합니다.|  
|[CHtmlView](../mfc/reference/chtmlview-class.md)|웹 브라우저 보기는 네트워크와 로컬 파일 시스템에 사용자 응용 프로그램의 사이트 폴더 뿐 아니라 World Wide Web에서를 찾을 수입니다. 액티브 문서 컨테이너도 웹 브라우저 보기를 사용할 수도 있습니다.|  
|[CRecordView](../mfc/reference/crecordview-class.md)|컨트롤에 ODBC 데이터베이스 레코드를 표시 하는 폼 보기입니다. 프로젝트에서 ODBC 지원을 선택한 경우에 보기의 기본 클래스는 `CRecordView`합니다. 에 연결 된 뷰는 `CRowset` 개체입니다.|  
|[CDaoRecordView](../mfc/reference/cdaorecordview-class.md)|컨트롤의 DAO 데이터베이스 레코드를 표시 하는 폼 보기입니다. 프로젝트에서 DAO 지원을 선택한 경우에 보기의 기본 클래스는 `CDaoRecordView`합니다. 에 연결 된 뷰는 `CDaoRecordset` 개체입니다.|  
|[COleDBRecordView](../mfc/reference/coledbrecordview-class.md)|컨트롤의 OLE DB 레코드를 표시 하는 폼 보기입니다. 프로젝트에 OLE DB 지원 기능을 선택한 경우에 보기의 기본 클래스는 `COleDBRecordView`합니다. 에 연결 된 뷰는 `CRowset` 개체입니다.|  
  
> [!NOTE]
>  MFC 버전 4.0 기준으로 `CEditView` 에서 파생 된 `CCtrlView`합니다.  
  
 응용 프로그램에서 이러한 클래스를 사용 하려면 응용 프로그램의 뷰 클래스에서 파생 되 합니다. 관련된 정보를 참조 하십시오. [스크롤 및 크기 조정 뷰](../mfc/scrolling-and-scaling-views.md)합니다. 데이터베이스 클래스에 대 한 자세한 내용은 참조 하십시오. [개요: 데이터베이스 프로그래밍](../data/data-access-programming-mfc-atl.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [뷰 사용](../mfc/using-views.md)

