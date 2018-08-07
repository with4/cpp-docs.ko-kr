---
title: 바로 가기 키 설정 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- keyboard shortcuts [MFC], hot keys
- access keys [MFC], hot keys
- CHotKeyCtrl class [MFC], setting hot key
ms.assetid: 6f3bc141-e346-4dce-9ca7-3e6b2c453f3f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3987ddee98ae35e02a181e38cd71f181801aeb61
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33379647"
---
# <a name="setting-a-hot-key"></a>바로 가기 키 설정
응용 프로그램 바로 가기 키 제공 하는 정보를 사용할 수 ([CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)) 다음 두 가지 방법 중 하나에서 제어 합니다.  
  
-   전송 하 여 비 자식 창을 활성화 하기 위한 전역 바로 가기 키를 설정 된 [WM_SETHOTKEY](http://msdn.microsoft.com/library/windows/desktop/ms646284) 창에 메시지를 활성화할 수 있습니다.  
  
-   Windows 함수를 호출 하 여 스레드 관련 바로 가기 키를 설정 [RegisterHotKey](http://msdn.microsoft.com/library/windows/desktop/ms646309)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CHotKeyCtrl 사용](../mfc/using-chotkeyctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

