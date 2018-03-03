---
title: "목록 컨트롤 및 목록 보기 | Microsoft Docs"
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
- CListView class [MFC], and CListCtrl
- views [MFC], list and list control
- CListCtrl class [MFC], and CListView
- list views [MFC]
- list controls [MFC], List view
ms.assetid: 7aee1c48-b158-4399-be0b-be366993665e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 46c9d559d642b6edf926b9feb49332ef7ec2924a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="list-control-and-list-view"></a>목록 컨트롤 및 목록 뷰
편의 위해 MFC는 두 가지 방법으로 목록 컨트롤을 캡슐화합니다. 목록 컨트롤을 사용할 수 있습니다.  
  
-   포함 하 여 직접는 [CListCtrl](../mfc/reference/clistctrl-class.md) 대화 상자 클래스에는 개체입니다.  
  
-   클래스를 사용 하 여 직접 [CListView](../mfc/reference/clistview-class.md)합니다.  
  
 `CListView`쉽게 목록 컨트롤 컨트롤을 캡슐화 하는 MFC 문서/뷰 아키텍처를 통합할 수 만큼 [CEditView](../mfc/reference/ceditview-class.md) 편집 컨트롤을 캡슐화: 컨트롤의 MFC 뷰로 전체 노출 영역을 채웁니다. (뷰 *은* 캐스팅 컨트롤 `CListView`.)  
  
 A `CListView` 개체에서 상속 [CCtrlView](../mfc/reference/cctrlview-class.md) 와 기본 클래스 기본 목록 컨트롤을 검색 하는 멤버 함수를 추가 합니다. 구성원 보기를 사용 하 여 뷰로 보기 작업을 합니다. 사용 하 여는 [GetListCtrl](../mfc/reference/clistview-class.md#getlistctrl) 멤버 함수는 목록 컨트롤의 멤버 함수에 대 한 액세스 권한을 얻으려고 합니다. 이러한 멤버를 사용 합니다.  
  
-   추가, 삭제 또는 목록에 "항목"을 조작 합니다.  
  
-   목록 컨트롤 특성을 가져오거나 설정 합니다.  
  
 에 대 한 참조를 가져올 수는 `CListCtrl` 기본는 `CListView`, 호출 `GetListCtrl` 목록 뷰 클래스에서:  
  
 [!code-cpp[NVC_MFCListView#4](../atl/reference/codesnippet/cpp/list-control-and-list-view_1.cpp)]  
  
 이 항목에는 목록 컨트롤을 사용 하도록 두 가지 방법을 모두 설명 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CListCtrl 사용](../mfc/using-clistctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

