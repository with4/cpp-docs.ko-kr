---
title: 상태 표시줄을 만드는 방법 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CStatusBar class [MFC], vs. CStatusBarCtrl
- methods [MFC], creating status bars
- CStatusBarCtrl class [MFC], vs. CStatusBar
- CStatusBarCtrl class [MFC], creating
- methods [MFC]
- status bars [MFC], creating
ms.assetid: 9aeaf290-7099-4762-a5ba-9c26705333c9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b0428bfc906ba6e8a1ecc7bd7c198327e8c31505
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="methods-of-creating-a-status-bar"></a>상태 표시줄을 만드는 방법
상태 표시줄을 만드는 두 개의 클래스를 제공 하는 MFC: [CStatusBar](../mfc/reference/cstatusbar-class.md) 및 [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md) (Windows 공용 컨트롤 API 래핑합니다 입니다). `CStatusBar` 모든 기능을 제공 표시줄 공용 컨트롤 상태를 자동으로 상호 작용 하는 메뉴 및 도구 모음, 하며 있습니다;에 대 한 대부분의 필수 공용 컨트롤 설정 및 구조 처리 그러나 결과 실행 파일이 일반적으로 보다 커집니다 사용 하 여 만든 `CStatusBarCtrl`합니다.  
  
 `CStatusBarCtrl` 일반적으로 결과 더 작은 실행 파일에 사용할 수도 `CStatusBarCtrl` MFC 아키텍처에 상태 표시줄을 통합 하지 않을 경우. 사용 하려는 경우 `CStatusBarCtrl` MFC 아키텍처에 상태 표시줄을 통합 하 고, 상태 표시줄 컨트롤 조작 MFC에 통신 하기 위해 추가 주의 해야 합니다. 이 통신이 어렵습니다. 그러나 사용할 때 필요 하지 않은 추가 작업은 `CStatusBar`합니다.  
  
 Visual c + + 공용 상태 표시줄 컨트롤을 활용 하는 두 가지를 제공 합니다.  
  
-   상태 표시줄를 사용 하 여 만들 `CStatusBar`, 한 다음 호출 [CStatusBar::GetStatusBarCtrl](../mfc/reference/cstatusbar-class.md#getstatusbarctrl) 에 액세스 하는 `CStatusBarCtrl` 멤버 함수입니다.  
  
-   상태 표시줄를 사용 하 여 만들 [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md)의 생성자입니다.  
  
 두 방법 중 하나는 상태 표시줄 컨트롤의 멤버 함수에 액세스할 수 있습니다. 호출 하는 경우 `CStatusBar::GetStatusBarCtrl`, 반환에 대 한 참조는 `CStatusBarCtrl` 개체 멤버 함수의 집합 중 하나를 사용할 수 있도록 합니다. 참조 [CStatusBar](../mfc/reference/cstatusbar-class.md) 생성 하 고 상태를 사용 하 여 표시줄 만들기에 대 한 내용은 `CStatusBar`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CStatusBarCtrl 사용](../mfc/using-cstatusbarctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

