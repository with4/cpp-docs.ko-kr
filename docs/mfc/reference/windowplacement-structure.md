---
title: "WINDOWPLACEMENT 구조체 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: WINDOWPLACEMENT
dev_langs: C++
helpviewer_keywords: WINDOWPLACEMENT structure [MFC]
ms.assetid: ea7d61f6-eb57-478e-9b08-7c1d07091aa8
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 333f6df7d704296903781f272be42eedbb7e1e1b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="windowplacement-structure"></a>WINDOWPLACEMENT 구조체
`WINDOWPLACEMENT` 화면의 창 배치에 대 한 정보를 포함 하는 구조**합니다.**  
  
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
 구조체의 바이트에서 길이 지정**합니다.**  
  
 `flags`  
 최소화 된 창을 및 창이 복원 됩니다 메서드의 위치를 제어 하는 플래그를 지정 합니다. 이 멤버는 하나 또는 둘 다 플래그 중 하나일 수 있습니다.  
  
- **WPF_SETMINPOSITION** 최소화 된 창의 x 및 y 위치를 지정할 수 있음을 지정**합니다.** 이 플래그 여야 합니다 좌표 설정 된 경우 지정 된 **ptMinPosition** 멤버입니다.  
  
- **WPF_RESTORETOMAXIMIZED** 는 복원된 된 창의 됩니다 수 최대화, 최소화 된 전에 최대화 되었는지는 여부에 관계 없이 지정 합니다. 이 설정은 다음에 창 복원할 때만 유효 합니다. 기본 복원 동작은 변경 되지 않습니다. 이 플래그는 경우에만 유효는 **SW_SHOWMINIMIZED** 에 값이 지정은 **showCmd** 멤버입니다.  
  
 *showCmd*  
 창의 현재 표시 상태를 지정합니다. 이 멤버는 다음 값 중 하나일 수 있습니다.  
  
- **SW_HIDE** 창을 숨깁니다 하 고 다른 창에 활성화를 전달 합니다.  
  
- **SW_MINIMIZE** 지정된 창을 최소화 하 고 시스템의 목록에서 최상위 창을 활성화 합니다.  
  
- **SW_RESTORE** 활성화 하 고 창을 표시 합니다. 창이, 최대화 또는 최소화 하는 경우 Windows에 복원의 원래 크기와 위치 (동일 **는 SW_SHOWNORMAL**).  
  
- **SW_SHOW** 의 현재 크기와 위치에 표시 하는 창을 활성화 합니다.  
  
- **SW_SHOWMAXIMIZED** 창을 활성화 하 고 최대화 창으로 표시 됩니다.  
  
- **SW_SHOWMINIMIZED** 창을 활성화 하 고 아이콘으로 표시 합니다.  
  
- **SW_SHOWMINNOACTIVE** 창을 아이콘으로 표시 합니다. 현재 활성화 된 창에 활성 상태로 유지 됩니다.  
  
- **SW_SHOWNA** 현재 상태에서 창을 표시 합니다. 현재 활성화 된 창에 활성 상태로 유지 됩니다.  
  
- **SW_SHOWNOACTIVATE** 의 가장 최근 크기와 위치의 창을 표시 합니다. 현재 활성화 된 창에 활성 상태로 유지 됩니다.  
  
- **SW_SHOWNORMAL** 활성화 하 고 창을 표시 합니다. 창이, 최대화 또는 최소화 하는 경우 Windows에 복원의 원래 크기와 위치 (동일 **SW_RESTORE**).  
  
 *ptMinPosition*  
 창이 최소화 되 때 창의 왼쪽 위 모서리의 위치를 지정 합니다.  
  
 `ptMaxPosition`  
 창이 최대화 되었을 때 창의 왼쪽 위 모서리의 위치를 지정 합니다.  
  
 *rcNormalPosition*  
 창이 기본 (복원된) 위치에 있을 때 창의 좌표를 지정 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** winuser.h  
  
## <a name="see-also"></a>참고 항목  
 [구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::SetWindowPlacement](../../mfc/reference/cwnd-class.md#setwindowplacement)

