---
title: "목록 상자 스타일 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
- LBS_NOSEL constant
- LBS_NOREDRAW constant
- LBS_HASSTRINGS constant
- LBS_OWNERDRAWFIXED constant
- LBS_WANTKEYBOARDINPUT constant
- LBS_STANDARD constant
- LBS_MULTIPLESEL constant
- LBS_OWNERDRAWVARIABLE constant
- LBS_DISABLENOSCROLL constant
- LBS_NODATA constant
- list boxes, styles
- LBS_EXTENDEDSEL constant
- LBS_MULTICOLUMN constant
- LBS_NOTIFY constant
- LBS_USETABSTOPS constant
- LBS_NOINTEGRALHEIGHT constant
- LBS_SORT constant
ms.assetid: 3f357b8d-9118-4f41-9e28-02ed92d1e88f
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
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 8e038e5cef50bd15df85c9d7f8b213b54ed03825
ms.lasthandoff: 02/24/2017

---
# <a name="list-box-styles"></a>목록 상자 스타일
-   **LBS_DISABLENOSCROLL** 목록 상자는 비활성화 된 세로 스크롤 막대의 경우 목록 상자는 스크롤할 수 만큼 항목을 표시 합니다. 이 스타일을 사용하지 않으면 목록 상자에 충분한 항목이 포함되지 않은 경우 스크롤 막대가 숨겨집니다.  
  
-   **LBS_EXTENDEDSEL** SHIFT 키와 마우스 또는 특수 키 조합을 사용 하 여 여러 항목을 선택할 수 있습니다.  
  
-   **LBS_HASSTRINGS** 문자열로 구성 된 항목을 포함 하는 소유자 그리기 목록 상자를 지정 합니다. 응용 프로그램에 사용할 수 있도록 하는 메모리 및 문자열에 대 한 포인터 목록 상자 유지는 `GetText` 특정 항목에 대 한 텍스트를 검색 하려면 멤버 함수입니다.  
  
-   **LBS_MULTICOLUMN** 가로로 스크롤 된 여러 열 목록 상자를 지정 합니다. `SetColumnWidth` 열의 너비를 설정 하는 멤버 함수입니다.  
  
-   **LBS_MULTIPLESEL** 문자열 선택 영역을 설정/해제 될 때마다 사용자가 클릭 하거나 문자열을 두 번 클릭 합니다. 임의 개수의 문자열을 선택할 수 있습니다.  
  
-   **LBS_NODATA** 데이터가 없는 목록 상자를 지정 합니다. 목록 상자에서 항목의 수는&1; 천을 초과 하는 경우이 스타일을 지정 합니다. 데이터가 없는 목록 상자 있어야는 **LBS_OWNERDRAWFIXED** 스타일을 하지만 있어서는 안는 **LBS_SORT** 또는 **LBS_HASSTRINGS** 스타일입니다.  
  
     데이터가 없는 목록 상자 항목에 대 한 문자열 또는 비트맵 데이터가 없는 포함 한다는 점을 제외 하면 소유자가 그린 목록 상자를 유사 합니다. 명령에 추가 하려면 삽입 또는 항목을 삭제할 데이터에 특정 항목을 항상 무시 요청 문자열을 찾는 목록 상자 내에서 항상 실패 합니다. 시스템 보냅니다는 `WM_DRAWITEM` 항목 그려야 할 때 소유자 창에 메시지를 합니다. itemID 멤버는 `DRAWITEMSTRUCT` 으로 전달 하는 구조는 `WM_DRAWITEM` 을 그릴 수 있도록 항목의 줄 번호를 지정 하는 메시지입니다. 데이터가 없는 목록 상자를 보내지 않습니다는 `WM_DELETEITEM` 메시지입니다.  
  
-   **LBS_NOINTEGRALHEIGHT** 목록 상자의 크기는 목록 상자를 만들 때 응용 프로그램에 의해 지정 된 크기에 정확 하 게 합니다. 일반적으로 Windows 목록 상자의 크기를 목록 상자 부분 항목을 표시 하지 않도록 합니다.  
  
-   **LBS_NOREDRAW** 목록 상자 표시에는 변경 될 때 업데이트 되지 않습니다. 전송 하 여 언제 든 지가이 스타일을 변경할 수 있습니다는 **WM_SETREDRAW** 메시지입니다.  
  
-   **LBS_NOSEL** 목록 상자 항목을 볼 수는 있지만 선택 하지 포함 되도록 지정 합니다.  
  
-   **LBS_NOTIFY** 부모 창은 사용자가 클릭 하거나 문자열을 두 번 클릭할 때마다 입력된 메시지를 수신 합니다.  
  
-   **LBS_OWNERDRAWFIXED** 목록 상자의 소유자는 해당 내용을 그리는 것은 목록 상자에 있는 항목 높이 같게 만들기.  
  
-   **LBS_OWNERDRAWVARIABLE** 목록 상자의 소유자는 해당 내용을 그리기; 목록 상자에 항목이 높이의 변수입니다.  
  
-   **LBS_SORT** 목록 상자에 문자열을 사전순으로 정렬 됩니다.  
  
-   **LBS_STANDARD** 목록 상자에는 문자열을 사전순으로 정렬 하 고 부모 창은 사용자가 클릭 하거나 문자열을 두 번 클릭할 때마다 입력된 메시지를 수신 합니다. 목록 상자에는 모든 면에 테두리가 포함 됩니다.  
  
-   **LBS_USETABSTOPS** 목록 상자를 인식 하 여 해당 문자열을 그릴 때 탭 문자를 확장할 수 있습니다. 기본 탭 위치는 32 대화 상자 단위입니다. (대화 상자 단위는 가로 또는 세로 거리를가 하는 데 사용 합니다. 하나의 가로 대화 상자 단위는 현재 대화 기본 너비 단위의&1; /&4;와 같습니다. 대화 상자 기본 단위는 현재 시스템 글꼴의 너비와 높이에 따라 계산 됩니다. **GetDialogBaseUnits** Windows 함수는 현재 대화 기본 단위 픽셀 단위로 반환 합니다.) 이 스타일와 사용할 수 없습니다 **LBS_OWNERDRAWFIXED**합니다.  
  
-   **LBS_WANTKEYBOARDINPUT** 소유자는 목록 상자에 받는 `WM_VKEYTOITEM` 또는 `WM_CHARTOITEM` 목록 상자에 입력 포커스가 있는 동안 키를 누를 때마다 메시지입니다. 따라서 키보드 입력에 특수 한 처리를 수행할 응용을 프로그램을 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC에서 사용 되는 스타일](../../mfc/reference/styles-used-by-mfc.md)   
 [CListBox::Create](../../mfc/reference/clistbox-class.md#create)   
 [목록 상자 스타일](http://msdn.microsoft.com/library/windows/desktop/bb775149)


