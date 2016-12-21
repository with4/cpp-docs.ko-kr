---
title: "콤보 상자 스타일 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CBS_LOWERCASE"
  - "CBS_SORT"
  - "CBS_OWNERDRAWVARIABLE"
  - "CBS_OEMCONVERT"
  - "CBS_AUTOHSCROLL"
  - "CBS_NOINTEGRALHEIGHT"
  - "CBS_SIMPLE"
  - "CBS_DROPDOWNLIST"
  - "CBS_DROPDOWN"
  - "CBS_UPPERCASE"
  - "CBS_HASSTRINGS"
  - "CBS_DISABLENOSCROLL"
  - "CBS_OWNERDRAWFIXED"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CBS_OWNERDRAWVARIABLE 상수"
  - "CBS_NOINTEGRALHEIGHT 상수"
  - "CBS_SIMPLE 상수"
  - "CBS_AUTOHSCROLL 상수"
  - "CBS_OEMCONVERT 상수"
  - "CBS_DISABLENOSCROLL 상수"
  - "CBS_HASSTRINGS 상수"
  - "CBS_LOWERCASE 상수"
  - "CBS_SORT 상수"
  - "CBS_DROPDOWN 상수"
  - "CBS_OWNERDRAWFIXED 상수"
  - "콤보 상자, 스타일"
  - "CBS_UPPERCASE 상수"
  - "CBS_DROPDOWNLIST 상수"
ms.assetid: d21a5023-e6a2-495b-a6bd-010a515cbc63
caps.latest.revision: 12
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 콤보 상자 스타일
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

다음 콤보 상자 스타일을 MFC에서 사용할 수 있습니다.  
  
-   **CBS\_AUTOHSCROLL** 사용자가 줄의 끝에 문자를 입력하면 편집 컨트롤의 텍스트가 자동으로 오른쪽으로 스크롤됩니다. 이 스타일을 설정하지 않으면 사각형 경계에 포함되는 텍스트만 허용됩니다.  
  
-   **CBS\_DISABLENOSCROLL** 목록 상자에 스크롤할 충분한 개수의 항목이 포함되지 않은 경우 비활성화된 세로 스크롤 막대가 표시됩니다. 이 스타일을 사용하지 않으면 목록 상자에 충분한 항목이 포함되지 않은 경우 스크롤 막대가 숨겨집니다.  
  
-   **CBS\_DROPDOWN** 사용자가 편집 컨트롤 옆의 아이콘을 선택하지 않은 경우 목록 상자가 표시되지 않는다는 점을 제외하고는 **CBS\_SIMPLE**과 유사합니다.  
  
-   **CBS\_DROPDOWNLIST** 편집 컨트롤이 목록 상자의 현재 선택 항목을 표시하는 정적 텍스트 항목으로 대체된다는 점을 제외하고는 **CBS\_DROPDOWN**과 유사합니다.  
  
-   **CBS\_HASSTRINGS** 소유자 그리기 콤보 상자에 문자열로 구성된 항목을 포함합니다. 콤보 상자는 응용 프로그램에서 `GetText` 멤버 함수를 사용하여 특정 항목에 대한 텍스트를 검색할 수 있도록 문자열에 대한 포인터 및 메모리를 유지합니다.  
  
-   **CBS\_LOWERCASE** 선택 필드와 목록의 모든 텍스트를 소문자로 변환합니다.  
  
-   **CBS\_NOINTEGRALHEIGHT** 콤보 상자의 크기가 콤보 상자를 만들 때 응용 프로그램에 지정된 크기와 정확히 일치하도록 지정합니다. 일반적으로 Windows에서는 콤보 상자에 특정 항목이 표시되지 않도록 콤보 상자의 크기를 지정합니다.  
  
-   **CBS\_OEMCONVERT** 콤보 상자 편집 컨트롤에 입력된 텍스트가 ANSI 문자 집합에서 OEM 문자 집합으로 변환된 다음 다시 ANSI로 변환됩니다. 따라서 응용 프로그램이 콤보 상자의 ANSI 문자열을 OEM 문자로 변환하기 위해 `AnsiToOem` Windows 함수를 호출할 때 문자가 적절히 변환됩니다. 이 스타일은 파일 이름을 포함하는 콤보 상자에 매우 유용하며 **CBS\_SIMPLE** 또는 **CBS\_DROPDOWN** 스타일로 만들어진 콤보 상자에만 적용됩니다.  
  
-   **CBS\_OWNERDRAWFIXED** 목록 상자의 소유자가 내용을 그립니다. 목록 상자의 항목은 높이가 모두 같습니다.  
  
-   **CBS\_OWNERDRAWVARIABLE** 목록 상자의 소유자가 내용을 그립니다. 목록 상자의 항목은 높이가 가변적입니다.  
  
-   **CBS\_SIMPLE** 목록 상자가 항상 표시 됩니다. 목록 상자에서 현재 선택된 항목이 편집 컨트롤에 표시됩니다.  
  
-   **CBS\_SORT** 목록 상자에 입력되는 문자열을 자동으로 정렬합니다.  
  
-   **CBS\_UPPERCASE** 선택 필드와 목록의 모든 텍스트를 대문자로 변환합니다.  
  
## 참고 항목  
 [MFC에서 사용하는 스타일](../../mfc/reference/styles-used-by-mfc.md)   
 [CComboBox::Create](../Topic/CComboBox::Create.md)   
 [Combo Box Styles](_win32_combo_box_styles)