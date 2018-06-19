---
title: 도구 설명 알림 처리 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- TOOLTIPTEXT structure [MFC]
- CToolBarCtrl class [MFC], handling notifications
- notifications [MFC], tool tips
- tool tips [MFC], notifications
ms.assetid: ddb93b5f-2e4f-4537-8053-3453c86e2bbb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3b9dffa2513c11a5feb3228cb4fdb1f6efbebe7a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33346378"
---
# <a name="handling-tool-tip-notifications"></a>도구 설명 알림 처리
지정 하는 경우는 `TBSTYLE_TOOLTIPS` 도구 모음 스타일을 만들고 도구 설명 컨트롤을 관리 합니다. 도구 설명에는 도구 모음 단추를 설명 하는 텍스트 줄을 포함 하는 작은 팝업 창인은 합니다. 사용자가 도구 모음 단추에 커서 있고 그대로 있을 약 절반에 대 한 두 번째 경우에 나타나는 도구 설명 숨겨져 있습니다. 커서 주위 도구 설명이 표시 됩니다.  
  
 도구 설명이 표시 되기 전에 **TTN_NEEDTEXT** 단추에 대 한 설명 텍스트를 검색 하 고 도구 모음 소유자 창에 알림 메시지가 보내집니다. 도구 모음의 소유자 창이 하는 경우는 `CFrameWnd` 때문에 설명이 추가 작업 없이 표시 되는 도구 창 `CFrameWnd` 에 대 한 기본 처리기는 **TTN_NEEDTEXT** 알림입니다. 도구 모음의 소유자 창에서 파생 되지 않은 경우 `CFrameWnd`, 대화 상자 또는 폼 보기와 같은 항목 소유자 창의 메시지 맵에 추가 하 고 메시지 맵에 알림 처리기를 제공 해야 합니다. 소유자 창의 메시지 맵에 항목은 다음과 같습니다.  
  
 [!code-cpp[NVC_MFCControlLadenDialog#40](../mfc/codesnippet/cpp/handling-tool-tip-notifications_1.cpp)]  
  
## <a name="remarks"></a>설명  
 `memberFxn`  
 이 단추 텍스트가 필요할 때 호출 되는 멤버 함수입니다.  
  
 도구 설명의 id는 항상 0입니다.  
  
 이외에 **TTN_NEEDTEXT** 알림, 도구 설명 컨트롤 도구 모음 컨트롤에는 다음과 같은 알림이 보낼 수 있습니다.  
  
|알림|의미|  
|------------------|-------------|  
|**TTN_NEEDTEXTA**|도구 설명 컨트롤 필요 ASCII 텍스트 (Windows 95에만 해당)|  
|**TTN_NEEDTEXTW**|도구 설명 컨트롤 필요 유니코드 텍스트 (Windows NT에만 해당)|  
|**TBN_HOTITEMCHANGE**|핫 (강조 된) 항목이 변경 되었음을 나타냅니다.|  
|**NM_RCLICK**|단추를 마우스 오른쪽 단추로 클릭 사용자가을 나타냅니다.|  
|**TBN_DRAGOUT**|사용자가 단추를 클릭 하 고 끌어 포인터를 단추 밖을 나타냅니다. 응용을 프로그램을 끌어서를 구현 하 고 도구 모음 단추에서 삭제할 수 있습니다. 이 알림을 받으면 응용 프로그램이 끌어서 시작과 놓기 작업 합니다.|  
|**TBN_DROPDOWN**|사용자가 사용 하는 단추 클릭 나타냅니다는 **TBSTYLE_DROPDOWN** 스타일입니다.|  
|**TBN_GETOBJECT**|사용자는 사용 하는 단추 위로 포인터를 이동 나타냅니다는 **TBSTYLE_DROPPABLE** 스타일입니다.|  
  
 예제 처리기 함수 및 도구 설명을 사용 하도록 설정 하는 방법에 대 한 자세한 내용은 참조 [도구 설명](../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CToolBarCtrl 사용](../mfc/using-ctoolbarctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

