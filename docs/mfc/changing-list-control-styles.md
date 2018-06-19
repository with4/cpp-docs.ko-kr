---
title: 목록 컨트롤 스타일 변경 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- styles [MFC], CListCtrl
- CListCtrl class [MFC], styles
- CListCtrl class [MFC], changing styles
ms.assetid: be74a005-0795-417c-9056-f6342aa74b26
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f9d93511ad4f4ca835e09b6eaa3f612f0888e844
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33344844"
---
# <a name="changing-list-control-styles"></a>목록 컨트롤 스타일 변경
목록 컨트롤의 창 스타일을 변경할 수 있습니다 ([CListCtrl](../mfc/reference/clistctrl-class.md)) 만든 후 언제 든 지 합니다. 창 스타일을 변경 하 여 보기를 사용 하 여 컨트롤의 종류를 변경 합니다. 예를 들어 탐색기를 에뮬레이트 하려면 제공할 수도 있습니다 메뉴 항목이 나 서로 다른 뷰 사이 있는 컨트롤을 전환 하기 위한 도구 모음 단추: 아이콘 보기, 목록 뷰 등에입니다.  
  
 예를 들어 사용자가 메뉴 항목을 선택 하도록 만드는 호출 [GetWindowLong](http://msdn.microsoft.com/library/windows/desktop/ms633584) 컨트롤의 현재 스타일을 검색 한 다음 호출 하 [SetWindowLong](http://msdn.microsoft.com/library/windows/desktop/ms633591) 스타일을 다시 설정 합니다. 자세한 내용은 참조 [목록 보기 컨트롤을 사용 하](http://msdn.microsoft.com/library/windows/desktop/bb774736) Windows sdk에서입니다.  
  
 사용 가능한 스타일에 나열 된 [만들기](../mfc/reference/clistctrl-class.md#create)합니다. 스타일 `LVS_ICON`, `LVS_SMALLICON`, `LVS_LIST`, 및 `LVS_REPORT` 4 개의 목록 컨트롤 뷰를 지정 합니다.  
  
## <a name="extended-styles"></a>확장된 스타일  
 목록 컨트롤에 대 한 표준 스타일을 외에도 확장된 스타일 라고 하는 다른 집합이 있습니다. 이러한 스타일의 경우에 설명 된 [확장 목록 보기 스타일](http://msdn.microsoft.com/library/windows/desktop/bb774732) Windows SDK에는 다양 한 목록 컨트롤의 동작을 사용자 지정 하는 유용한 기능을 제공 합니다. 확인에 대 한 호출 (예: 가리키기 선택) 스타일의 동작을 구현 하려면 [CListCtrl::SetExtendedStyle](../mfc/reference/clistctrl-class.md#setextendedstyle), 필요한 스타일을 전달 합니다. 다음 예제에서는 함수 호출을 보여 줍니다.  
  
 [!code-cpp[NVC_MFCControlLadenDialog#22](../mfc/codesnippet/cpp/changing-list-control-styles_1.cpp)]  
  
> [!NOTE]
>  실행 되도록 가리키기 선택에 있어야 **LVS_EX_ONECLICKACTIVATE** 또는 **LVS_EX_TWOCLICKACTIVATE** 켜져 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [CListCtrl 사용](../mfc/using-clistctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

