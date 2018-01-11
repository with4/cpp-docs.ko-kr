---
title: "MFC의 상태 표시줄 구현 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: COldStatusBar
dev_langs: C++
helpviewer_keywords:
- status bars [MFC], implementing in MFC
- CStatusBarCtrl class [MFC], and MFC status bars
- CStatusBar class [MFC], and CStatusBarCtrl class [MFC]
- CStatusBarCtrl class [MFC], and CStatusBar class [MFC]
- status bars [MFC], backward compatibility
- status bars [MFC], old with COldStatusBar class [MFC]
- COldStatusBar class [MFC]
- status bars [MFC], and CStatusBarCtrl class
- CStatusBar class [MFC], and MFC status bars
- status indicators
- status bars [MFC], Windows 95 implementation
ms.assetid: be5cd876-38e3-4d5c-b8cb-16d57a16a142
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4d81982e23f100fe75d6cc5769cd19359bfaa6f5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="status-bar-implementation-in-mfc"></a>MFC의 상태 표시줄 구현
A [CStatusBar](../mfc/reference/cstatusbar-class.md) 개체 텍스트 출력 창 행이 있는 컨트롤 막대입니다. 출력 창 및 상태 표시기 메시지 선으로 자주 사용 됩니다. 선택 된 메뉴 명령을 간략하게 설명 하는 메뉴 도움말 메시지 줄 및 SCROLL LOCK, NUM LOCK 및 다른 키의 상태를 나타내는 표시기를 예로 들 수 있습니다.  
  
 클래스를 사용 하 여 상태 표시줄은 구현 하는 MFC 버전 4.0부터 [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md), 상태 표시줄 공용 컨트롤을 캡슐화 하는 합니다. 이전 버전과 호환성에 대 한 MFC 유지 클래스의 이전 상태 표시줄 구현 **COldStatusBar**합니다. 이전 버전의 MFC에 대 한 설명서에서 설명 **COldStatusBar** 아래 `CStatusBar`합니다.  
  
 [CStatusBar::GetStatusBarCtrl](../mfc/reference/cstatusbar-class.md#getstatusbarctrl), 멤버 함수 새 MFC 4.0 허용 상태 표시줄 사용자 지정 및 추가 기능에 대 한 Windows 공용 컨트롤 지원 기능을 사용할 수 있습니다. `CStatusBar`멤버 함수는 대부분의 Windows 공용 컨트롤; 기능 제공. 그러나 호출 하는 경우 `GetStatusBarCtrl`, 상태 표시줄의 특징 중 이상용으로 상태 표시줄을 제공할 수 있습니다. 호출 하는 경우 `GetStatusBarCtrl`에 대 한 참조를 반환 합니다는 `CStatusBarCtrl` 개체입니다. 상태 표시줄 컨트롤을 조작 하기 위한 해당 참조를 사용할 수 있습니다.  
  
 다음 그림은 여러 표시기를 표시 하는 상태 표시줄입니다.  
  
 ![상태 표시줄](../mfc/media/vc37dy1.gif "vc37dy1")  
상태 표시줄  
  
 도구 모음 같은 상태 표시줄 개체 부모 프레임 창에 포함 되어 있으며 프레임 창이 생성 될 때 자동으로 생성 됩니다. 모든 컨트롤 막대와 같은 상태 표시줄은 자동으로 소멸 부모 프레임 소멸 될 때입니다.  
  
## <a name="what-do-you-want-to-know-more-about"></a>에 대 한 자세한 내용을 하 시겠습니까  
  
-   [상태 표시줄 창의 텍스트 업데이트](../mfc/updating-the-text-of-a-status-bar-pane.md)  
  
-   MFC 클래스 [CStatusBar](../mfc/reference/cstatusbar-class.md) 및 [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md)  
  
-   [컨트롤 막대](../mfc/control-bars.md)  
  
-   [대화 상자 모음](../mfc/dialog-bars.md)  
  
-   [도구 모음 (MFC 도구 모음 구현)](../mfc/mfc-toolbar-implementation.md)  
  
## <a name="see-also"></a>참고 항목  
 [상태 표시줄](../mfc/status-bars.md)

