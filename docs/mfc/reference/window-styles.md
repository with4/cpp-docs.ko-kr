---
title: "창 스타일 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- WS_MINIMIZEBOX
- WS_SIZEBOX
- WS_CLIPCHILDREN
- WS_TILED
- WS_GROUP
- WS_VSCROLL
- WS_CHILD
- WS_TABSTOP
- WS_HSCROLL
- WS_THICKFRAME
- WS_DISABLED
- WS_POPUP
- WS_ICONIC
- WS_MAXIMIZE
- WS_VISIBLE
- WS_POPUPWINDOW
- WS_TILEDWINDOW
- WS_DLGFRAME
- WS_MINIMIZE
- WS_CAPTION
- WS_OVERLAPPED
- WS_BORDER
- WS_MAXIMIZEBOX
- WS_OVERLAPPEDWINDOW
- WS_SYSMENU
- WS_CHILDWINDOW
- WS_CLIPSIBLINGS
dev_langs:
- C++
helpviewer_keywords:
- WS_THICKFRAME constant
- WS_TILEDWINDOW constant
- WS_MAXIMIZEBOX constant
- WS_DLGFRAME constant
- WS_CHILDWINDOW constant
- window styles, in MFC
- WS_CHILD constant
- WS_GROUP constant
- WS_MINIMIZE constant
- WS_CAPTION constant
- WS_MAXIMIZE constant
- WS_POPUP constant
- WS_SYSMENU constant
- WS_TILED constant
- window styles
- WS_POPUPWINDOW constant
- WS_CLIPSIBLINGS constant
- WS_BORDER constant
- WS_DISABLED constant
- WS_VSCROLL constant
- WS_OVERLAPPED constant
- WS_MINIMIZEBOX constant
- WS_VISIBLE constant
- WS_OVERLAPPEDWINDOW constant
- WS_TABSTOP constant
- WS_ICONIC constant
- WS_SIZEBOX constant
- WS_HSCROLL constant
- WS_CLIPCHILDREN constant
- styles, windows
ms.assetid: c85ffbe4-f4ff-4227-917a-48ec4a411842
caps.latest.revision: 12
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: d814e3a10132fb3fe88969ce434f8286b02afba5
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="window-styles"></a>창 스타일
-   `WS_BORDER`테두리가 있는 창을 만듭니다.  
  
-   **WS_CAPTION** 제목 표시줄에 있는 창을 만드는 (의미는 `WS_BORDER` 스타일). 와 함께 사용할 수는 **WS_DLGFRAME** 스타일입니다.  
  
-   **WS_CHILD** 자식 창을 만듭니다. 와 함께 사용할 수는 `WS_POPUP` 스타일입니다.  
  
-   **WS_CHILDWINDOW** 동일는 **WS_CHILD** 스타일입니다.  
  
-   **WS_CLIPCHILDREN** 자식 창을 부모 창 내에서 그릴 때 사용 하 고 영역을 제외 합니다. 부모 창을 만들 때 사용 합니다.  
  
-   **WS_CLIPSIBLINGS** 서로 상대적인 클립 자식 창, 즉 특정 자식 창에는 그리기 메시지를 받을 경우는 **WS_CLIPSIBLINGS** 스타일 업데이트할 자식 창을 지역 외부에서 다른 모든 중첩된 자식 창 자릅니다. (경우 **WS_CLIPSIBLINGS** 제공 되지 않습니다 이므로 자식 창이 겹쳐, 자식 창의 클라이언트 영역 내에서 그릴 때, 인접 한 자식 창의 클라이언트 영역 내에 그릴 수 있습니다.) 와 함께 사용할는 **WS_CHILD** 스타일만 합니다.  
  
-   **WS_DISABLED** 사용 하지 않도록 처음으로 창을 만듭니다.  
  
-   **WS_DLGFRAME** 이중 테두리가 있지만 제목이 없는 창을 만듭니다.  
  
-   **WS_GROUP** 를 이동할 수 한 컨트롤에서 다음 화살표 키를 가진 컨트롤 그룹의 첫 번째 컨트롤을 지정 합니다. 정의 된 모든 컨트롤은 **WS_GROUP** 스타일 **FALSE** 후 첫 번째 컨트롤은 동일한 그룹에 속해야 합니다. 사용 하 여 다음 컨트롤은 **WS_GROUP** 스타일 다음 그룹 (즉, 하나의 그룹 끝 다음 시작 되는 위치)를 시작 합니다.  
  
-   **WS_HSCROLL** 가로 스크롤 막대가 있는 창을 만듭니다.  
  
-   **WS_ICONIC** 처음 최소화 하는 창을 만듭니다. 동일는 **WS_MINIMIZE** 스타일입니다.  
  
-   **WS_MAXIMIZE** 최대 크기의 창을 만듭니다.  
  
-   **WS_MAXIMIZEBOX** 최대화 단추가 포함 된 창을 만듭니다.  
  
-   **WS_MINIMIZE** 처음 최소화 하는 창을 만듭니다. 와 함께 사용할는 **WS_OVERLAPPED** 스타일만 합니다.  
  
-   **WS_MINIMIZEBOX** 최소화 단추가 포함 된 창을 만듭니다.  
  
-   **WS_OVERLAPPED** overlapped 창을 만듭니다. 캡션 및 테두리에 일반적으로 overlapped 창에 있습니다.  
  
-   **WS_OVERLAPPEDWINDOW** 와 겹치는 창을 만듭니다는 **WS_OVERLAPPED**, **WS_CAPTION**, **WS_SYSMENU**, **WS_THICKFRAME**, **WS_MINIMIZEBOX**, 및 **WS_MAXIMIZEBOX** 스타일입니다.  
  
-   `WS_POPUP`팝업 창을 만듭니다. 와 함께 사용할 수는 **WS_CHILD** 스타일입니다.  
  
-   **WS_POPUPWINDOW** 으로 팝업 창을 만드는 `WS_BORDER`, `WS_POPUP`, 및 **WS_SYSMENU** 스타일입니다. **WS_CAPTION** 스타일과 조합 해야는 **WS_POPUPWINDOW** 스타일을 컨트롤 메뉴를 표시 합니다.  
  
-   **WS_SIZEBOX** 크기 조정 테두리가 있는 창을 만듭니다. 동일는 **WS_THICKFRAME** 스타일입니다.  
  
-   **WS_SYSMENU** 의 제목 표시줄에 컨트롤 메뉴 상자 창을 만듭니다. 제목 표시줄 windows에만 사용 합니다.  
  
-   **WS_TABSTOP** 는 사용자가 TAB 키를 사용 하 여 이동할 수는 컨트롤의 여러 언어 중 하나를 지정 합니다. TAB 키를 누를 사용자로 지정 된 다음 컨트롤로 이동는 **WS_TABSTOP** 스타일입니다.  
  
-   **WS_THICKFRAME** 창 크기를 사용할 수 있는 두꺼운 프레임 창을 만듭니다.  
  
-   **WS_TILED** overlapped 창을 만듭니다. Overlapped는 창 제목 표시줄 및 테두리에 있습니다. 동일는 **WS_OVERLAPPED** 스타일입니다.  
  
-   **WS_TILEDWINDOW** 와 겹치는 창을 만듭니다는 **WS_OVERLAPPED**, **WS_CAPTION**, **WS_SYSMENU**, **WS_THICKFRAME**, **WS_MINIMIZEBOX**, 및 **WS_MAXIMIZEBOX** 스타일입니다. 동일는 **WS_OVERLAPPEDWINDOW** 스타일입니다.  
  
-   **WS_VISIBLE** 처음 표시 되는 창을 만듭니다.  
  
-   **WS_VSCROLL** 세로 스크롤 막대가 있는 창을 만듭니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC에서 사용 되는 스타일](../../mfc/reference/styles-used-by-mfc.md)   
 [CWnd::Create](../../mfc/reference/cwnd-class.md#create)   
 [CWnd::CreateEx](../../mfc/reference/cwnd-class.md#createex)   
 [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679)


