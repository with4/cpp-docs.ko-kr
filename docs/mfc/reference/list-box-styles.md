---
title: "목록 상자 스타일 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- LBS_STANDARD
- LBS_NODATA
- LBS_OWNERDRAWVARIABLE
- LBS_EXTENDEDSEL
- LBS_USETABSTOPS
- LBS_WANTKEYBOARDINPUT
- LBS_NOTIFY
- LBS_DISABLENOSCROLL
- LBS_HASSTRINGS
- LBS_NOREDRAW
- LBS_NOSEL
- LBS_NOINTEGRALHEIGHT
- LBS_MULTICOLUMN
- LBS_SORT
- LBS_MULTIPLESEL
- LBS_OWNERDRAWFIXED
dev_langs:
- C++
helpviewer_keywords:
- LBS_NOSEL constant [MFC]
- LBS_NOREDRAW constant [MFC]
- LBS_HASSTRINGS constant [MFC]
- LBS_OWNERDRAWFIXED constant [MFC]
- LBS_WANTKEYBOARDINPUT constant [MFC]
- LBS_STANDARD constant [MFC]
- LBS_MULTIPLESEL constant [MFC]
- LBS_OWNERDRAWVARIABLE constant [MFC]
- LBS_DISABLENOSCROLL constant [MFC]
- LBS_NODATA constant [MFC]
- list boxes [MFC], styles
- LBS_EXTENDEDSEL constant [MFC]
- LBS_MULTICOLUMN constant [MFC]
- LBS_NOTIFY constant [MFC]
- LBS_USETABSTOPS constant [MFC]
- LBS_NOINTEGRALHEIGHT constant [MFC]
- LBS_SORT constant
ms.assetid: 3f357b8d-9118-4f41-9e28-02ed92d1e88f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8f52734e26d1965811aded67bc1e1dde6a2c28bc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="list-box-styles"></a>목록 상자 스타일
-   **LBS_DISABLENOSCROLL** 목록 상자 표시 비활성화 된 세로 스크롤 막대의 목록 상자에 스크롤할 충분 한 항목이 없습니다. 이 스타일을 사용하지 않으면 목록 상자에 충분한 항목이 포함되지 않은 경우 스크롤 막대가 숨겨집니다.  
  
-   **LBS_EXTENDEDSEL** SHIFT 키와 마우스 또는 특수 키 조합을 사용 하 여 여러 항목을 선택할 수 있습니다.  
  
-   **LBS_HASSTRINGS** 문자열로 구성 된 항목을 포함 하는 소유자 그리기 목록 상자를 지정 합니다. 응용 프로그램에서 사용할 수 있도록 문자열에 대 한 포인터 및 메모리 유지를 목록 상자는 `GetText` 특정 항목에 대 한 텍스트를 검색 하려면 멤버 함수입니다.  
  
-   **LBS_MULTICOLUMN** 가로로 스크롤되는 여러 열 목록 상자를 지정 합니다. `SetColumnWidth` 멤버 함수는 열의 너비를 설정 합니다.  
  
-   **LBS_MULTIPLESEL** 문자열 선택 영역을 설정/해제 될 때마다 사용자가 클릭 하거나 문자열을 두 번 클릭 합니다. 임의 개수의 문자열을 선택할 수 있습니다.  
  
-   **LBS_NODATA** 데이터가 없는 목록 상자를 지정 합니다. 목록 상자에 있는 항목 수는 1 천을 초과 했을 때이 스타일을 지정 합니다. 데이터가 없는 목록 상자 있어야는 **LBS_OWNERDRAWFIXED** 스타일을 가져서는 안 되지만 **LBS_SORT** 또는 **LBS_HASSTRINGS** 스타일입니다.  
  
     데이터가 없는 목록 상자에 소유자가 그린 목록 상자와 유사 제외 하 고 항목에 대 한 string 또는 bitmap 데이터가 없는 포함 합니다. 명령에 추가 하려면 삽입 또는 항목을 삭제할 데이터; 특정 항목을 항상 무시 요청 문자열을 찾으려면 목록 상자 내에서 항상 실패 합니다. 시스템은 보냅니다는 `WM_DRAWITEM` 항목 그려야 할 때 소유자 창에 메시지입니다. itemID 멤버는 `DRAWITEMSTRUCT` 구조와 함께 전달는 `WM_DRAWITEM` 메시지를 그릴 수 있도록 항목의 줄 번호를 지정 합니다. 데이터가 없는 목록 상자를 전송 하지 않습니다는 `WM_DELETEITEM` 메시지입니다.  
  
-   **LBS_NOINTEGRALHEIGHT** 목록 상자의 크기는 목록 상자를 만들 때 응용 프로그램에서 지정 된 크기와 정확히 일치 합니다. 일반적으로 Windows 목록 상자의 크기를 목록 상자 부분 항목을 표시 하지 않도록 합니다.  
  
-   **LBS_NOREDRAW** 변경 사항이 있을 경우 목록 상자 디스플레이가 업데이트 되지 않습니다. 이 스타일 전송 하 여 언제 든 지 변경할 수 있습니다는 **WM_SETREDRAW** 메시지입니다.  
  
-   **LBS_NOSEL** 목록 상자 항목을 볼 수 있지만 선택 하지 않은 포함 되도록 지정 합니다.  
  
-   **LBS_NOTIFY** 를 클릭 하거나 문자열을 두 번 클릭할 때마다 부모 창 입력된 메시지를 받습니다.  
  
-   **LBS_OWNERDRAWFIXED** 목록 상자의 소유자가 내용을 되며 다음 목록 상자의 항목 높이 같게 만들기.  
  
-   **LBS_OWNERDRAWVARIABLE** 목록 상자의 소유자가 내용을 않으면 목록 상자에 있는 항목은 높이가 가변적입니다.  
  
-   **LBS_SORT** 문자열 목록 상자에서 사전순으로 정렬 됩니다.  
  
-   **LBS_STANDARD** 문자열 목록 상자에서 사전순으로 정렬 되 고를 클릭 하거나 문자열을 두 번 클릭할 때마다 부모 창 입력된 메시지를 받습니다. 목록 상자에는 모든 면에 테두리가 포함 되어 있습니다.  
  
-   **LBS_USETABSTOPS** 목록 상자를 인식 하 고 해당 문자열을 그릴 때 탭 문자를 확장할 수 있습니다. 기본 탭 위치는 32 대화 상자 단위입니다. (대화 상자 단위는 가로 또는 세로 거리입니다. 하나의 가로 대화 상자 단위는 현재 대화 기본 두께 단위의 1 / 4와 같습니다. 대화 상자 기본 단위는 현재 시스템 글꼴의 너비와 높이에 따라 계산 됩니다. **GetDialogBaseUnits** Windows 함수 현재 대화 상자 기본 단위 픽셀 단위로 반환 합니다.) 이 스타일와 사용할 수 없습니다 **LBS_OWNERDRAWFIXED**합니다.  
  
-   **LBS_WANTKEYBOARDINPUT** 목록 상자의 소유자 받는 `WM_VKEYTOITEM` 또는 `WM_CHARTOITEM` 목록 상자에 입력 포커스가 있는 동안 사용자가 키 때마다 메시지입니다. 따라서 입력 하 고 키보드에서 특수 한 처리를 수행할 응용을 프로그램을 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC에서 사용 되는 스타일](../../mfc/reference/styles-used-by-mfc.md)   
 [CListBox::Create](../../mfc/reference/clistbox-class.md#create)   
 [목록 상자 스타일](http://msdn.microsoft.com/library/windows/desktop/bb775149)

