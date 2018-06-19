---
title: 수동으로 컨트롤 추가 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Windows common controls [MFC], adding
- dialog box controls [MFC], adding to dialog boxes
- controlling input focus
- input focus control
- focus, controlling input [MFC]
- controls [MFC], adding to dialog boxes
- common controls [MFC], adding
ms.assetid: bc843e59-0c51-4b5b-8bf2-343f716469d2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: efe510c4376255c24470a799b5dde17021894bf0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33342477"
---
# <a name="adding-controls-by-hand"></a>수동으로 컨트롤 추가
다음 중 하나 [대화 상자 편집기와 대화 상자에 컨트롤 추가](../mfc/using-the-dialog-editor-to-add-controls.md) 하거나 코드를 직접 추가 합니다.  
  
 컨트롤 개체를 직접 만들려면 일반적으로 c + + 대화 상자에서 c + + 컨트롤 개체 또는 프레임 창 개체를 포함 합니다. 프레임 워크의 여러 다른 개체 처럼 컨트롤 2 단계 생성을 해야합니다. 컨트롤의 호출 해야 **만들기** 부모 대화 상자 또는 프레임 창 만들기의 일부로 멤버 함수입니다. 대화 상자에 대 한 일반적으로 이렇게 [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog), 및 프레임 창에서 [OnCreate](../mfc/reference/cwnd-class.md#oncreate)합니다.  
  
 다음 예제에서는 방법을 선언할 수 있습니다는 `CEdit` 개체에서 파생 된 대화 상자 클래스의 클래스 선언 하 고 호출 하는 **만들기** 멤버 함수에 `OnInitDialog`합니다. 때문에 `CEdit` 개체가 포함 된 개체로 선언 된 대화 상자 개체를 생성 하지만 자체와 여전히 초기화 해야 때 자동으로 구성 됩니다, **만들기** 멤버 함수입니다.  
  
 [!code-cpp[NVC_MFCControlLadenDialog#1](../mfc/codesnippet/cpp/adding-controls-by-hand_1.h)]  
  
 다음 `OnInitDialog` 사각형을 설정 하는 함수 호출 **만들기** Windows 편집 컨트롤을 만들고이 연결 하는 초기화 되지 않은 `CEdit` 개체입니다.  
  
 [!code-cpp[NVC_MFCControlLadenDialog#2](../mfc/codesnippet/cpp/adding-controls-by-hand_2.cpp)]  
  
 편집 개체를 만든 후 설정할 수 있습니다도 입력된 포커스가 컨트롤을 호출 하 여는 `SetFocus` 멤버 함수입니다. 0을 반환 하는 마지막으로, `OnInitDialog` 포커스를 설정 하면 표시 됩니다. 0이 아닌 값을 반환 하는 경우 대화 상자 관리자 대화 상자 항목 목록에서 첫 번째 컨트롤 항목으로 포커스를 설정 합니다. 대부분의 경우에서 대화 상자 편집기와 대화 상자에 컨트롤을 추가 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [컨트롤 만들기 및 사용](../mfc/making-and-using-controls.md)   
 [컨트롤](../mfc/controls-mfc.md)   
 [CDialog::OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog)

