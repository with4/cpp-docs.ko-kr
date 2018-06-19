---
title: WINDOWPOS 구조 1 | Microsoft Docs
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
ms.openlocfilehash: d4abd236998f37f0d719f41827d05a17fde56fde
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33379296"
---
# <a name="windowpos-structure1"></a>WINDOWPOS 구조 1
`WINDOWPOS` 구조는 창의 위치와 크기에 대 한 정보를 포함 합니다.  
  
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
 이 창을 배치 되는 뒤에 있는 창을 식별 합니다.  
  
 *x*  
 창의 왼쪽된 가장자리의 위치를 지정합니다.  
  
 *y*  
 창의 오른쪽 가장자리의 위치를 지정 합니다.  
  
 `cx`  
 창 너비를 픽셀 단위로 지정 합니다.  
  
 `cy`  
 창의 높이 픽셀 단위로 지정 합니다.  
  
 `flags`  
 창 위치 지정 옵션을 지정합니다. 이 멤버는 다음 값 중 하나일 수 있습니다.  
  
- **SWP_DRAWFRAME** 창 주위 프레임 (창에 대 한 클래스 설명에 정의 됨)를 그립니다. 받습니다는 `WM_NCCALCSIZE` 메시지입니다.  
  
- **SWP_FRAMECHANGED** 보냅니다는 `WM_NCCALCSIZE` 는 창 크기가 변경 되는 경우에 창에는 메시지입니다. 이 플래그를 지정 하지 않으면 `WM_NCCALCSIZE` 창 크기가 변경 되는 경우에 전송 됩니다.  
  
- **SWP_HIDEWINDOW** 창을 숨깁니다.  
  
- `SWP_NOACTIVATE` 창을 활성화 하지 않습니다.  
  
- **SWP_NOCOPYBITS** 클라이언트 영역의 전체 내용을 삭제 합니다. 이 플래그를 지정 하지 클라이언트 영역의 유효한 내용은 저장 되며 창이 크기가 조정 되거나 위치가 변경 후 클라이언트 영역에 다시 복사 됩니다.  
  
- `SWP_NOMOVE` 현재 위치를 유지 (무시는 **x** 및 **y** 멤버).  
  
- **SWP_NOOWNERZORDER** Z-순서에서 소유자 창의 위치를 변경 되지 않습니다.  
  
- `SWP_NOSIZE` 현재 크기를 유지 하면서 (무시는 **cx** 및 **cy** 멤버).  
  
- **SWP_NOREDRAW** 변경 내용을 다시 그려지지 않습니다.  
  
- **SWP_NOREPOSITION** 동일 **SWP_NOOWNERZORDER**합니다.  
  
- **SWP_NOSENDCHANGING** 창을 받지 못하게에서 방지는 `WM_WINDOWPOSCHANGING` 메시지입니다.  
  
- `SWP_NOZORDER` 현재 순서 유지 (무시는 **hwndInsertAfter** 멤버).  
  
- **SWP_SHOWWINDOW** 창을 표시 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** winuser.h  
  
## <a name="see-also"></a>참고 항목  
 [구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnWindowPosChanging](../../mfc/reference/cwnd-class.md#onwindowposchanging)

