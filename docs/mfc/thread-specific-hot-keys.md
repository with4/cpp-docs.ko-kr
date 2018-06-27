---
title: 스레드 관련 바로 가기 키 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CHotKeyCtrl class [MFC], thread-specific hot keys
- keyboard shortcuts [MFC], hot keys
- threading [MFC], hot keys in CHotKeyCtrl
- access keys [MFC], hot keys
ms.assetid: b6021274-1498-483f-bcbf-ba5723547cc8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 14da7f0e5b0adbe72b6705700c1e9298751bc345
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36953611"
---
# <a name="thread-specific-hot-keys"></a>스레드 관련 바로 가기 키
스레드 관련 바로 가기 키를 설정 하는 응용 프로그램 ([CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)) Windows를 사용 하 여 `RegisterHotKey` 함수입니다. 스레드 관련 바로 가기 키를 누를 때 Windows 게시는 [WM_HOTKEY](http://msdn.microsoft.com/library/windows/desktop/ms646279) 특정 스레드의 메시지 큐의 시작 부분에는 메시지입니다. WM_HOTKEY 메시지 가상 키 코드, shift 상태 및 눌린 특정 바로 가기 키의 사용자 정의 ID를 포함 합니다. 표준 가상 키 코드 목록이 Winuser.h을 참조 하세요. 이 메서드에 대 한 자세한 내용은 참조 하십시오. [RegisterHotKey](http://msdn.microsoft.com/library/windows/desktop/ms646309)합니다.  
  
 호출에 사용 되는 이동 상태 플래그를 지정 하는 참고 `RegisterHotKey` 반환한 것과 동일 하지 않습니다는 [GetHotKey](../mfc/reference/chotkeyctrl-class.md#gethotkey) ; 멤버 함수를 호출 하기 전에 이러한 플래그를 변환 해야 합니다. `RegisterHotKey`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CHotKeyCtrl 사용](../mfc/using-chotkeyctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

