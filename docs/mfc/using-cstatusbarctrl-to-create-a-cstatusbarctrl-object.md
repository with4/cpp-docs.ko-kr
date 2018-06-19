---
title: CStatusBarCtrl을 사용 하 여 CStatusBarCtrl 개체 만들기를 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CStatusBarCtrl
dev_langs:
- C++
helpviewer_keywords:
- status bar controls [MFC], creating
- CStatusBarCtrl class [MFC], creating
ms.assetid: 365c2b65-12de-49e6-9a2e-416c6ee10d60
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3b7f322003a36d89927930c0a57fd060078755f9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33383021"
---
# <a name="using-cstatusbarctrl-to-create-a-cstatusbarctrl-object"></a>CStatusBarCtrl을 사용하여 CStatusBarCtrl 개체 만들기
일반적인 사용의 예로 [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md):  
  
### <a name="to-use-a-status-bar-control-with-parts"></a>부분과 상태 표시줄 컨트롤을 사용 하려면  
  
1.  `CStatusBarCtrl` 개체를 생성합니다.  
  
2.  호출 [SetMinHeight](../mfc/reference/cstatusbarctrl-class.md#setminheight) 상태 표시줄 컨트롤의 최소 높이 설정 하려면 그리기 영역입니다.  
  
3.  호출 [SetBkColor](../mfc/reference/cstatusbarctrl-class.md#setbkcolor) 상태 표시줄 컨트롤의 배경색을 설정 합니다.  
  
4.  호출 [SetParts](../mfc/reference/cstatusbarctrl-class.md#setparts) 상태 표시줄 컨트롤, 각 파트의 오른쪽 가장자리의 좌표에에서 파트 수를 설정할 수 있습니다.  
  
5.  호출 [SetText](../mfc/reference/cstatusbarctrl-class.md#settext) 상태 표시줄 컨트롤의 지정된 된 부분에서 텍스트를 설정 합니다. 메시지는 컨트롤에서 변경된 부분을 무효화하고 이 컨트롤이 다음에 `WM_PAINT` 메시지를 수신할 때 새 텍스트가 표시되도록 합니다.  
  
 일부 경우 상태 표시줄 텍스트의 줄을 표시할지만 필요 합니다. 이 경우에 대 한 호출을 확인 [SetSimple](../mfc/reference/cstatusbarctrl-class.md#setsimple)합니다. 한 줄 텍스트를 표시 하는 "단순" 모드로 상태 표시줄 컨트롤을 추가 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CStatusBarCtrl 사용](../mfc/using-cstatusbarctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

