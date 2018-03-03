---
title: "전역 바로 가기 키 | Microsoft Docs"
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
- keyboard shortcuts [MFC], hot keys
- CHotKeyCtrl class [MFC], global hot keys
- access keys [MFC], hot keys
- global hot keys [MFC]
ms.assetid: e0b95d14-c571-4c9a-9cd1-e7fc1f0e278d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 82297507d8725e6292def759272f48d0d63e84b8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="global-hot-keys"></a>전역 바로 가기 키
전역 바로 가기 키가 특정 비 자식 창에 연결 합니다. 시스템의 모든 부분에서 창을 활성화 하려면 사용자 수 있습니다. 전송 하 여 특정 창에 대 한 전역 바로 가기 키를 설정 하는 응용 프로그램의 [WM_SETHOTKEY](http://msdn.microsoft.com/library/windows/desktop/ms646284) 해당 창에 메시지입니다. 예를 들어 경우 `m_HotKeyCtrl` 는 [CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md) 개체 및 `pMainWnd` 대 한 포인터 바로 가기 키를 누를 때 활성화할 창에 있는 컨트롤에 지정 된 바로 가기 키를 연결 하려면 다음 코드를 사용할 수 있습니다 창에서 가리키는 `pMainWnd`합니다.  
  
 [!code-cpp[NVC_MFCControlLadenDialog#18](../mfc/codesnippet/cpp/global-hot-keys_1.cpp)]  
  
 지정 된 창의 받는 전역 바로 가기 키를 누를 때마다는 [WM_SYSCOMMAND](http://msdn.microsoft.com/library/windows/desktop/ms646360) 지정 하는 메시지 **SC_HOTKEY** 명령 유형으로 합니다. 이 메시지는 수신 하는 창을 활성화 됩니다. 이 메시지는 정확한 키를 눌렀는지에 대 한 정보를 포함 되지 않았으므로,이 메서드를 사용 하 여 없도록 같은 창에 추가 될 수 있는 다른 바로 가기 키를 구별 합니다. 응용 프로그램에 전송 될 때까지 바로 가기 키 유효 **WM_SETHOTKEY** 종료 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [CHotKeyCtrl 사용](../mfc/using-chotkeyctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

