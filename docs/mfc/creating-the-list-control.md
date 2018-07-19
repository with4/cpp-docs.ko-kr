---
title: 목록 컨트롤 만들기 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CListCtrl class [MFC], creating control
- list controls [MFC]
ms.assetid: a4cb1729-31b6-4d2b-a44b-367474848a39
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 42457e223bb7e12da64be54d757e05d0bac3a028
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33342048"
---
# <a name="creating-the-list-control"></a>목록 컨트롤 만들기
목록 제어 하는 방법 ([CListCtrl](../mfc/reference/clistctrl-class.md)) 만들어질 컨트롤을 직접 사용 하거나 클래스를 사용 하 여 하 고 있는지 여부에 따라 달라 집니다 [CListView](../mfc/reference/clistview-class.md) 대신 합니다. 사용 하는 경우 `CListView`, 프레임 워크의 문서/뷰 만들기 시퀀스의 일부로 뷰를 만듭니다. 목록 보기를 만드는 컨트롤을 만듭니다는 목록도 (두 개의 동일한 작업 되어 있음). 보기의에서 컨트롤을 만들 [OnCreate](../mfc/reference/cwnd-class.md#oncreate) 처리기 함수입니다. 이 경우 컨트롤은 호출을 통해 항목을 추가할 수 있도록 준비 된 [GetListCtrl](../mfc/reference/clistview-class.md#getlistctrl)합니다.  
  
### <a name="to-use-clistctrl-directly-in-a-dialog-box"></a>CListCtrl 대화 상자에서 직접 사용 하려면  
  
1.  대화 상자 편집기에서 대화 상자 템플릿 리소스에는 목록 컨트롤을 추가 합니다. 해당 컨트롤 ID를 지정합니다.  
  
2.  사용 하 여는 [멤버 변수 추가 마법사](../ide/adding-a-member-variable-visual-cpp.md) 형식의 멤버 변수를 추가 하려면 `CListCtrl` 컨트롤 속성을 사용 합니다. 이 멤버를 사용하여 `CListCtrl` 멤버 함수를 호출할 수 있습니다.  
  
3.  모든 목록 컨트롤 알림 메시지에 대 한 대화 상자 클래스의 처리기 함수에 매핑할 속성 창에서 처리 해야 하는 사용 하 여 (참조 [함수에 메시지 매핑](../mfc/reference/mapping-messages-to-functions.md)).  
  
4.  [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog), 스타일을 설정는 `CListCtrl`합니다. 참조 [목록 컨트롤 스타일 변경](../mfc/changing-list-control-styles.md)합니다. 뷰를 나중에 변경할 수 있지만 컨트롤에서 얻게 "보기"의 종류를 결정 합니다.  
  
### <a name="to-use-clistctrl-in-a-nondialog-window"></a>CListCtrl 비 모달 창에서 사용 하려면  
  
1.  뷰 또는 창 클래스에서 컨트롤을 정의합니다.  
  
2.  컨트롤의 호출 [만들기](../mfc/reference/clistctrl-class.md#create) 멤버 함수를 [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate)부모 창의 만큼, [OnCreate](../mfc/reference/cwnd-class.md#oncreate) 처리기 함수 (인 경우 컨트롤을 서브클래싱하). 컨트롤의 스타일을 설정합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CListCtrl 사용](../mfc/using-clistctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

