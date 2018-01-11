---
title: "도구 모음을 작성 하는 방법 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- CToolBarCtrl class [MFC], and CToolBar class [MFC]
- CToolBar class [MFC], creating toolbars
- MFC toolbars
- toolbar controls [MFC]
- toolbar controls [MFC], creating
- CToolBarCtrl class [MFC], creating toolbars
ms.assetid: f19d8d65-d49f-445c-abe8-d47d3e4101c8
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6d93f8e43c933e9c8054e798c11754cc48bf54a5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="methods-of-creating-a-toolbar"></a>도구 모음을 만드는 방법
MFC 도구 모음을 만드는 두 개의 클래스를 제공: [CToolBar](../mfc/reference/ctoolbar-class.md) 및 [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) (Windows 공용 컨트롤 API 래핑합니다 입니다). `CToolBar`모든 도구 모음 공용 컨트롤의 기능을 제공 하면;에 대 한 대부분의 필수 공용 컨트롤 설정 및 구조를 처리 하 고 그러나 결과 실행 파일이 일반적으로 보다 커집니다 사용 하 여 만든 `CToolBarCtrl`합니다.  
  
 `CToolBarCtrl`일반적으로 결과 더 작은 실행 파일에 사용할 수도 `CToolBarCtrl` MFC 아키텍처에 도구 모음을 통합 하지 않을 경우. 사용 하려는 경우 `CToolBarCtrl` MFC 아키텍처에 도구 모음을 통합 하 고, MFC에 도구 모음 컨트롤 조작 통신 하기 위해 추가 주의 해야 합니다. 이 통신이 어렵습니다. 그러나 사용할 때 필요 하지 않은 추가 작업은 `CToolBar`합니다.  
  
 Visual c + + 도구 모음 공용 컨트롤을 활용 하는 두 가지를 제공 합니다.  
  
-   사용 하 여 도구 모음 만들기 `CToolBar`, 한 다음 호출 [CToolBar::GetToolBarCtrl](../mfc/reference/ctoolbar-class.md#gettoolbarctrl) 에 액세스 하는 `CToolBarCtrl` 멤버 함수입니다.  
  
-   사용 하 여 도구 모음 만들기 [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)의 생성자입니다.  
  
 두 방법 중 하나는 도구 모음 컨트롤의 멤버 함수에 액세스할 수 있습니다. 호출 하는 경우 `CToolBar::GetToolBarCtrl`, 반환에 대 한 참조는 `CToolBarCtrl` 개체 멤버 함수의 집합 중 하나를 사용할 수 있도록 합니다. 참조 [CToolBar](../mfc/reference/ctoolbar-class.md) 생성 하 고 사용 하 여 도구 모음 만들기에 대 한 내용은 `CToolBar`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CToolBarCtrl 사용](../mfc/using-ctoolbarctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

