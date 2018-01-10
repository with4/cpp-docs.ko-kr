---
title: "탭 컨트롤 만들기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- TCS_EX_REGISTERDROP
- TCS_EX_FLATSEPARATORS
dev_langs: C++
helpviewer_keywords:
- TCS_EX_REGISTERDROP extended style [MFC]
- tab controls [MFC], creating
- CTabCtrl class [MFC], creating
- TCS_EX_FLATSEPARATORS extended style
ms.assetid: 3a9c2d64-f5f4-41ea-84ab-fceb73c3dbdc
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 91349f46e577a2a433217f84d9e028139eb09c9d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="creating-the-tab-control"></a>탭 컨트롤 만들기
탭 컨트롤을 만들 방법을 대화 상자에서 컨트롤 사용 또는 비 모달 창에서 만드는 인지에 따라 달라 집니다.  
  
### <a name="to-use-ctabctrl-directly-in-a-dialog-box"></a>CTabCtrl 대화 상자에서 직접 사용 하려면  
  
1.  대화 상자 편집기에서 탭 컨트롤이 대화 상자 템플릿 리소스를 추가 합니다. 해당 컨트롤 ID를 지정합니다.  
  
2.  사용 하 여는 [멤버 변수 추가 마법사](../ide/adding-a-member-variable-visual-cpp.md) 형식의 멤버 변수를 추가 하려면 [CTabCtrl](../mfc/reference/ctabctrl-class.md) 컨트롤 속성을 사용 합니다. 이 멤버를 사용하여 `CTabCtrl` 멤버 함수를 호출할 수 있습니다.  
  
3.  처리 되는 모든 탭 컨트롤 알림 메시지에 대 한 대화 상자 클래스의 처리기 함수를 매핑하십시오. 자세한 내용은 참조 [함수에 메시지 매핑](../mfc/reference/mapping-messages-to-functions.md)합니다.  
  
4.  [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog), 스타일을 설정는 `CTabCtrl`합니다.  
  
### <a name="to-use-ctabctrl-in-a-nondialog-window"></a>CTabCtrl 비 모달 창에서 사용 하려면  
  
1.  뷰 또는 창 클래스에서 컨트롤을 정의합니다.  
  
2.  컨트롤의 호출 [만들기](../mfc/reference/ctabctrl-class.md#create) 멤버 함수를 [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate)부모 창의 만큼, [OnCreate](../mfc/reference/cwnd-class.md#oncreate) 처리기 함수 (인 경우 컨트롤을 서브클래싱하). 컨트롤의 스타일을 설정합니다.  
  
 후의 `CTabCtrl` 개체가 생성 되었음을, 설정 하거나 선택을 취소 다음 확장 스타일 수 있습니다.  
  
-   **TCS_EX_FLATSEPARATORS** 탭 컨트롤은 탭 항목 간의 구분 기호를 그립니다. 이 확장 스타일에만 영향을 줌 탭이 있는 컨트롤의 **TCS_BUTTONS** 및 **TCS_FLATBUTTONS** 스타일입니다. 기본적으로 사용 하 여 탭 컨트롤 만들기는 **TCS_FLATBUTTONS** 이 확장 스타일을 설정 하는 스타일입니다.  
  
-   **TCS_EX_REGISTERDROP** 탭 컨트롤 생성 **TCN_GETOBJECT** 컨트롤의 탭 항목에 대해 개체를 끌 때 알림 메시지를 요청 놓기 대상 개체입니다.  
  
    > [!NOTE]
    >  받을 수는 **TCN_GETOBJECT** 알림을 OLE 라이브러리를 호출 하 여 초기화 해야 [AfxOleInit](../mfc/reference/ole-initialization.md#afxoleinit)합니다.  
  
 이러한 스타일을 검색 컨트롤 만들어진 후에, 해당 호출을 통해 설정 하 고는 [GetExtendedStyle](../mfc/reference/ctabctrl-class.md#getextendedstyle) 및 [SetExtendedStyle](../mfc/reference/ctabctrl-class.md#setextendedstyle) 멤버 함수입니다.  
  
 예를 들어, 설정 된 **TCS_EX_FLATSEPARATORS** 스타일 코드의 다음 줄으로:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#33](../mfc/codesnippet/cpp/creating-the-tab-control_1.cpp)]  
  
 지우기는 **TCS_EX_FLATSEPARATORS** 에서 스타일을 `CTabCtrl` 코드의 다음 줄이 포함 된 개체:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#34](../mfc/codesnippet/cpp/creating-the-tab-control_2.cpp)]  
  
 단추 사이 표시 되는 구분 기호를 제거 합니다 프로그램 `CTabCtrl` 개체입니다.  
  
## <a name="see-also"></a>참고 항목  
 [CTabCtrl 사용](../mfc/using-ctabctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

