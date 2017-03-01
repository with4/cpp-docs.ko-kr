---
title: "정적 스타일 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SS_SUNKEN
- SS_CENTER
- SS_ENHMETAFILE
- SS_RIGHT
- SS_BLACKRECT
- SS_LEFTNOWORDWRAP
- SS_GRAYFRAME
- SS_USERITEM
- SS_GRAYRECT
- SS_WHITEFRAME
- SS_ETCHEDFRAME
- SS_ETCHEDVERT
- SS_WHITERECT
- SS_PATHELLIPSIS
- SS_WORDELLIPSIS
- SS_NOPREFIX
- SS_BITMAP
- SS_SIMPLE
- SS_CENTERIMAGE
- SS_BLACKFRAME
- SS_OWNERDRAW
- SS_REALSIZEIMAGE
- SS_RIGHTJUST
- SS_ICON
- SS_NOTIFY
- SS_ETCHEDHORZ
- SS_LEFT
- SS_ENDELLIPSIS
dev_langs:
- C++
helpviewer_keywords:
- SS_ICON constant
- SS_WHITEFRAME constant
- SS_BLACKFRAME constant
- SS_ETCHEDHORZ constant
- SS_OWNERDRAW constant
- SS_BITMAP constant
- SS_NOPREFIX constant
- SS_NOTIFY constant
- SS_CENTER constant
- SS_REALSIZEIMAGE constant
- SS_ETCHEDFRAME constant
- SS_CENTERIMAGE constant
- SS_SUNKEN constant
- SS_ENDELLIPSIS constant
- SS_WORDELLIPSIS constant
- SS_WHITERECT constant
- SS_ETCHEDVERT constant
- SS_GRAYFRAME constant
- SS_LEFTNOWORDWRAP constant
- SS_LEFT constant
- SS_SIMPLE constant
- static styles
- SS_ENHMETAFILE constant
- SS_GRAYRECT constant
- SS_USERITEM constant
- SS_PATHELLIPSIS constant
- SS_BLACKRECT constant
- SS_RIGHT constant
- SS_RIGHTJUST constant
ms.assetid: a1114548-fc6d-491d-8c46-21d11b8574f5
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
ms.openlocfilehash: ad34c688fdfd3c2b4c81a0a03fbce53a905162ad
ms.lasthandoff: 02/24/2017

---
# <a name="static-styles"></a>정적 스타일
-   **SS_BITMAP** 정적 컨트롤에 표시 되는 비트맵을 지정 합니다. 지정된 된 텍스트에는 리소스 파일에서 다른 곳에서 정의 하는 비트맵 (파일 이름이 아닌)의 이름입니다. 스타일에서는 nWidth 및 nHeight 매개 변수를 무시합니다. 컨트롤 크기를 자동으로 비트맵에 맞게 자체입니다.  
  
-   **SS_BLACKFRAME** 프레임 창 프레임이 같은 색을 사용 하 여 그린 상자를 지정 합니다. 기본값은 검정입니다.  
  
-   **SS_BLACKRECT** 창 프레임을 그리는 데 사용 되는 색으로 채워진 사각형을 지정 합니다. 기본값은 검정입니다.  
  
-   **SS_CENTER** 간단한 사각형을 지정 하 고 가운데 사각형에 지정된 된 텍스트를 표시 합니다. 텍스트가 표시 되기 전에 서식이 지정 됩니다. 줄의 끝을 지나서 확장 적용 하는 단어는 자동으로 가운데 맞춤 된 다음 줄의 시작 부분으로 래핑됩니다.  
  
-   **SS_CENTERIMAGE** 를 비트맵 이나 아이콘 정적 컨트롤의 클라이언트 영역 보다 작은 경우 나머지 클라이언트 영역을 채우도록 지정 합니다 비트맵 이나 아이콘의 왼쪽된 위 모퉁이에 있는 픽셀의 색을 사용 합니다. 정적 컨트롤의 텍스트 한 줄이 있으면 텍스트 중앙에 세로로 컨트롤의 클라이언트 영역에 있습니다.  
  
-   **SS_ENDELLIPSIS** 또는 **SS_PATHELLIPSIS** 일부 바꿉니다. 지정된 된 문자열의 타원, 필요한 경우 결과 지정 된 사각형에 사용할 수 있도록 합니다.  
  
     지정할 수 있습니다 **SS_END_ELLIPSIS** 문자열의 끝에 문자를 바꿀 또는 **SS_PATHELLIPSIS** 문자열 가운데 문자를 바꿀 합니다. 문자열에 있는 경우 백슬래시 (\\) 문자를 **SS_PATHELLIPSIS** 유지 만큼 텍스트의 마지막 백슬래시 다음 가능한 합니다.  
  
-   **SS_ENHMETAFILE** 정적 컨트롤에 표시 되는 확장된 메타 파일을 지정 합니다. 지정된 된 텍스트에는 메타 파일의 이름입니다. 확장된 메타 파일 정적 컨트롤에는 고정된 크기입니다. 메타 파일 정적 컨트롤의 클라이언트 영역에 맞게 크기가 조정 됩니다.  
  
-   **SS_ETCHEDFRAME** 사용 하 여 정적 컨트롤의 프레임 그립니다는 **EDGE_ETCHED** 스타일 가장자리입니다.  
  
-   **SS_ETCHEDHORZ** 그립니다 사용 하 여 정적 컨트롤의 위쪽 및 아래쪽 가장자리는 **EDGE_ETCHED** 스타일 가장자리입니다.  
  
-   **SS_ETCHEDVERT** EDGE_ETCHED 가장자리 스타일을 사용 하 여 정적 컨트롤의 왼쪽 및 오른쪽 가장자리를 그립니다.  
  
-   **SS_GRAYFRAME** 같은 색으로 화면 배경 (바탕 화면)를 사용 하 여 그린 프레임이 있는 상자를 지정 합니다. 기본값은 회색입니다.  
  
-   **SS_GRAYRECT** 화면 배경을 채우는 데 사용 되는 색으로 채워진 사각형을 지정 합니다. 기본값은 회색입니다.  
  
-   **SS_ICON** 대화 상자에 표시 되는 아이콘을 지정 합니다. 지정된 된 텍스트에는 다른 곳에서 정의 되는 리소스 파일에서 아이콘 (파일 이름이 아닌)의 이름입니다. `nWidth` 및 `nHeight` 아이콘 크기를 자동으로 자체; 매개 변수가 무시 됩니다.  
  
-   **SS_LEFT** 간단한 사각형을 지정 하 고 지정된 된 텍스트 사각형에서 왼쪽 플러시를 표시 합니다. 텍스트가 표시 되기 전에 서식이 지정 됩니다. 단어 줄의 끝을 지나서 이어지는 다음 플러시 왼쪽 줄의 시작 부분으로 자동으로 래핑됩니다.  
  
-   **SS_LEFTNOWORDWRAP** 간단한 사각형을 지정 하 고 지정된 된 텍스트 사각형에서 왼쪽 플러시를 표시 합니다. 탭 확장 되어 있지만 단어 래핑되지 않습니다. 줄의 끝을 지나서 확장 하는 텍스트가 잘립니다.  
  
-   **SS_NOPREFIX** 이 스타일을 지정 하지 않으면 Windows 엑셀 러 레이 터 접두사 문자로 컨트롤의 텍스트에 앰퍼샌드 (&) 문자를 해석 합니다. 이 경우에 앰퍼샌드 제거 되 고 문자열의 다음 문자에 밑줄이 표시 됩니다. 여기서이 기능은 사용 하지 않으려는 정적 컨트롤은 텍스트를 포함 하는 경우 **SS_NOPREFIX** 추가 될 수 있습니다. 이 정적 컨트롤 스타일 정의 된 정적 컨트롤 중 하나라도 포함 될 수 있습니다. 결합할 수 **SS_NOPREFIX** 비트 OR 연산자를 사용 하 여 다른 스타일을 사용 합니다. 이 대화 상자에서 정적 컨트롤에 표시 되는 앰퍼샌드를 포함할 수 있는 다른 문자열 또는 파일 이름이 필요할 때 가장 자주 사용 됩니다.  
  
-   **SS_NOTIFY** 부모 창 보냅니다 **STN_CLICKED**, **STN_DBLCLK**, **STN_DISABLE**, 및 **STN_ENABLE** 알림 메시지를 사용자가 클릭 하거나 컨트롤을 두 번 클릭 합니다.  
  
-   **SS_OWNERDRAW** 정적 컨트롤의 소유자 그리기 컨트롤에 대 한 책임 임을 지정 합니다. 소유자 창은 수신 하는 `WM_DRAWITEM` 컨트롤을 그려야 할 때마다 메시지입니다.  
  
-   **SS_REALSIZEIMAGE** 정적 아이콘 또는 비트맵 컨트롤이 그려지지 않습니다 (즉, 정적 컨트롤에는 **SS_ICON** 또는 **SS_BITMAP** 스타일)의 로드 하거나 그릴 때 크기 조정 합니다. 아이콘 또는 비트맵 대상 영역 보다 큰 경우 이미지가 잘립니다.  
  
-   **SS_RIGHT** 간단한 사각형을 지정 하 고 플러시 오른쪽 사각형에 지정된 된 텍스트를 표시 합니다. 텍스트가 표시 되기 전에 서식이 지정 됩니다. 단어 줄의 끝을 지나서 이어지는 다음 플러시 오른쪽 줄의 시작 부분으로 자동으로 래핑됩니다.  
  
-   **SS_RIGHTJUST** 지정 된 정적 컨트롤의 오른쪽 아래 모서리는 **SS_BITMAP** 또는 **SS_ICON** 스타일은 컨트롤 크기를 조정할 때 고정 합니다. 위쪽 및 왼쪽 면만 새 비트맵 이나 아이콘에 맞게 조정 됩니다.  
  
-   **SS_SIMPLE** 간단한 사각형을 지정 하 고 플러시 왼쪽 사각형에 텍스트 한 줄을 표시 합니다. 텍스트 줄을 축소 하거나 어떠한 방식으로든 변경 될 수 없습니다. (컨트롤의 부모 창 또는 대화 상자를 처리 해야는 `WM_CTLCOLOR` 메시지입니다.)  
  
-   **SS_SUNKEN** 정적 컨트롤 주위 절반 오목 테두리를 그립니다.  
  
-   **SS_USERITEM** 사용자 정의 항목을 지정 합니다.  
  
-   **SS_WHITEFRAME** 프레임 창 배경과 같은 색을 사용 하 여 그린 상자를 지정 합니다. 기본값은 흰색입니다.  
  
-   **SS_WHITERECT** 창 배경을 채우는 데 사용 되는 색으로 채워진 사각형을 지정 합니다. 기본값은 흰색입니다.  
  
-   **SS_WORDELLIPSIS** 맞지 않는 하며 타원을 추가 하는 텍스트를 잘라냅니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC에서 사용 되는 스타일](../../mfc/reference/styles-used-by-mfc.md)   
 [CStatic::Create](../../mfc/reference/cstatic-class.md#create)   
 [DrawEdge](http://msdn.microsoft.com/library/windows/desktop/dd162477)   
 [정적 컨트롤 스타일](http://msdn.microsoft.com/library/windows/desktop/bb760773)


