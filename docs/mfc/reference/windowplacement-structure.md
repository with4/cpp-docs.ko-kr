---
title: WINDOWPLACEMENT 구조체 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- WINDOWPLACEMENT
dev_langs:
- C++
helpviewer_keywords:
- WINDOWPLACEMENT structure [MFC]
ms.assetid: ea7d61f6-eb57-478e-9b08-7c1d07091aa8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6dbd9a921194146e260eb79f5266311caa3d0300
ms.sourcegitcommit: 76fd30ff3e0352e2206460503b61f45897e60e4f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/13/2018
ms.locfileid: "39026197"
---
# <a name="windowplacement-structure"></a>WINDOWPLACEMENT 구조체
`WINDOWPLACEMENT` 구조 화면의 창에 배치 하는 방법에 대 한 정보가 들어 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef struct tagWINDOWPLACEMENT {     /* wndpl */  
    UINT length;  
    UINT flags;  
    UINT showCmd;  
    POINT ptMinPosition;  
    POINT ptMaxPosition;  
    RECT rcNormalPosition;  
} WINDOWPLACEMENT;  
```  
  
#### <a name="parameters"></a>매개 변수  
*length*  
구조체의 바이트에서 길이 지정 합니다.  
  
*flags*  
최소화 된 창 및 창 복원 되는 메서드의 위치를 제어 하는 플래그를 지정 합니다. 이 멤버는 다음 플래그 중 하나 또는 모두 일 수 있습니다.  
  
 - WPF_SETMINPOSITION 최소화 된 창의 x 및 y 위치를 지정할 수 있음을 지정 합니다. 이 플래그 여야 합니다 좌표에서 설정 하는 경우 지정 된 된 `ptMinPosition` 멤버입니다.  
      
 - WPF_RESTORETOMAXIMIZED는 복원 된 창이 됩니다 수 최대화, 최소화 된 상태의 전에 최대화 되었는지는 여부에 관계 없이 지정 합니다. 이 설정은 창을 복원 된 다음에 유효 합니다. 기본값 복원 동작을 변경 하지는 않습니다. SW_SHOWMINIMIZED 값을 지정 하는 경우에이 플래그는 잘못 된 `showCmd` 멤버입니다.  
  
*showCmd*  
창의 현재 상태 표시를 지정합니다. 이 멤버는 다음 값 중 하나일 수 있습니다.  
  
 - SW_HIDE 창을 숨깁니다 하 고 다른 창으로 정품 인증을 전달 합니다.  
      
 - SW_MINIMIZE는 지정된 된 창을 최소화 하 고 시스템의 목록에서 최상위 창을 활성화 합니다.  
      
 - SW_RESTORE 활성화 하 고 창을 표시 합니다. 창이 최소화 또는 최대화, 경우 Windows 원래 크기와 위치 (는 SW_SHOWNORMAL 동일)을 복원 합니다.  
      
 - SW_SHOW는 창을 활성화 한 현재 크기 및 위치에 표시 됩니다.  
      
 - SW_SHOWMAXIMIZED 창을 활성화 하는 최대화 된 창으로 표시 합니다.  
      
 - SW_SHOWMINIMIZED 창을 활성화 하는 아이콘으로 표시 합니다.  
      
 - SW_SHOWMINNOACTIVE는 아이콘으로 창을 표시 합니다. 현재 활성 창에 활성 상태로 유지 됩니다.  
      
 - SW_SHOWNA 현재 상태에서 창을 표시 합니다. 현재 활성 창에 활성 상태로 유지 됩니다.  
      
 - SW_SHOWNOACTIVATE 가장 최근 크기와 위치는 창을 표시 합니다. 현재 활성 창에 활성 상태로 유지 됩니다.  
      
 - SW_SHOWNORMAL 활성화 하 고 창을 표시 합니다. 창이 최소화 또는 최대화, 경우 Windows 원래 크기와 위치 (SW_RESTORE 동일)을 복원 합니다.  
  
*ptMinPosition*  
창을 최소화 하는 경우 창의 왼쪽 위 모퉁이 위치를 지정 합니다.  
  
*ptMaxPosition*  
최대화 하는 경우 창의 왼쪽 위 모퉁이 위치를 지정 합니다.  
  
*rcNormalPosition*  
창이 일반 (복원된) 위치에 있을 때 창의 좌표를 지정 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** winuser.h  
  
## <a name="see-also"></a>참고 항목  
 [구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::SetWindowPlacement](../../mfc/reference/cwnd-class.md#setwindowplacement)

