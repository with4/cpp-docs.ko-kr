---
title: WINDOWPOS 구조체 1 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- WINDOWPOS
dev_langs:
- C++
helpviewer_keywords:
- WINDOWPOS structure [MFC]
ms.assetid: a4ea7cd9-c4c2-4480-9c55-cbbff72195e1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: db51e8f9924d69406989b3a9ac12b45f0e55e870
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37885964"
---
# <a name="windowpos-structure1"></a>WINDOWPOS 구조체 1
`WINDOWPOS` 구조 크기와 창에 위치 하는 방법에 대 한 정보가 들어 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef struct tagWINDOWPOS { /* wp */  
    HWND hwnd;  
    HWND hwndInsertAfter;  
    int x;  
    int y;  
    int cx;  
    int cy;  
    UINT flags;  
} WINDOWPOS;  
```  
  
#### <a name="parameters"></a>매개 변수  
 *hwnd*  
 창을 식별 합니다.  
  
 *hwndInsertAfter*  
 이 창 뒤 위치한 창을 식별 합니다.  
  
 *x*  
 창의 왼쪽된 가장자리의 위치를 지정 합니다.  
  
 *y*  
 창의 오른쪽 가장자리의 위치를 지정 합니다.  
  
 *cx*  
 창 너비를 픽셀 단위로 지정 합니다.  
  
 *cy*  
 창 높이 픽셀 단위로 지정합니다.  
  
 *flags*  
 창 위치 지정 옵션을 지정합니다. 이 멤버는 다음 값 중 하나일 수 있습니다.  
  
- SWP_DRAWFRAME 창 주위 프레임 (창 클래스 설명에 정의 됨)를 그립니다. 창은 WM_NCCALCSIZE 메시지를 받습니다.  
  
- SWP_FRAMECHANGED 보냅니다는 WM_NCCALCSIZE 메시지 창으로 창의 크기를 변경 되는 경우에 합니다. 이 플래그를 지정 하지 않으면 WM_NCCALCSIZE 창의 크기가 변경 되는 경우에 전송 됩니다.  
  
- SWP_HIDEWINDOW 창을 숨깁니다.  
  
- 창을 활성화 되지 SWP_NOACTIVATE 않습니다.  
  
- SWP_NOCOPYBITS는 클라이언트 영역의 전체 내용을 삭제합니다. 이 플래그를 지정 하지 않으면 클라이언트 영역의 올바른 콘텐츠 저장 되며 창이 크기 또는 위치가 변경 되 면 클라이언트 영역에 다시 복사 됩니다.  
  
- 현재 위치 SWP_NOMOVE 유지 (무시 합니다 `x` 및 `y` 멤버).  
  
- Z-순서에서 소유자 창의 위치를 변경할 SWP_NOOWNERZORDER 않습니다.  
  
- 현재 크기 SWP_NOSIZE 유지 (무시 합니다 `cx` 및 `cy` 멤버).  
  
- 변경 내용을 다시 그려지지 SWP_NOREDRAW 않습니다.  
  
- SWP_NOREPOSITION SWP_NOOWNERZORDER 동일 합니다.  
  
- SWP_NOSENDCHANGING은 WM_WINDOWPOSCHANGING 메시지 수신을 창을 방지 합니다.  
  
- 현재 정렬 SWP_NOZORDER 유지 (무시는 `hwndInsertAfter` 멤버).  
  
- SWP_SHOWWINDOW 창을 표시합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** winuser.h  
  
## <a name="see-also"></a>참고 항목  
 [구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnWindowPosChanging](../../mfc/reference/cwnd-class.md#onwindowposchanging)

