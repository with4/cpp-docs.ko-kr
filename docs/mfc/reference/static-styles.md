---
title: "정적 스타일 | Microsoft Docs"
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
  - "SS_SUNKEN"
  - "SS_CENTER"
  - "SS_ENHMETAFILE"
  - "SS_RIGHT"
  - "SS_BLACKRECT"
  - "SS_LEFTNOWORDWRAP"
  - "SS_GRAYFRAME"
  - "SS_USERITEM"
  - "SS_GRAYRECT"
  - "SS_WHITEFRAME"
  - "SS_ETCHEDFRAME"
  - "SS_ETCHEDVERT"
  - "SS_WHITERECT"
  - "SS_PATHELLIPSIS"
  - "SS_WORDELLIPSIS"
  - "SS_NOPREFIX"
  - "SS_BITMAP"
  - "SS_SIMPLE"
  - "SS_CENTERIMAGE"
  - "SS_BLACKFRAME"
  - "SS_OWNERDRAW"
  - "SS_REALSIZEIMAGE"
  - "SS_RIGHTJUST"
  - "SS_ICON"
  - "SS_NOTIFY"
  - "SS_ETCHEDHORZ"
  - "SS_LEFT"
  - "SS_ENDELLIPSIS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SS_BITMAP 상수"
  - "SS_BLACKFRAME 상수"
  - "SS_BLACKRECT 상수"
  - "SS_CENTER 상수"
  - "SS_CENTERIMAGE 상수"
  - "SS_ENDELLIPSIS 상수"
  - "SS_ENHMETAFILE 상수"
  - "SS_ETCHEDFRAME 상수"
  - "SS_ETCHEDHORZ 상수"
  - "SS_ETCHEDVERT 상수"
  - "SS_GRAYFRAME 상수"
  - "SS_GRAYRECT 상수"
  - "SS_ICON 상수"
  - "SS_LEFT 상수"
  - "SS_LEFTNOWORDWRAP 상수"
  - "SS_NOPREFIX 상수"
  - "SS_NOTIFY 상수"
  - "SS_OWNERDRAW 상수"
  - "SS_PATHELLIPSIS 상수"
  - "SS_REALSIZEIMAGE 상수"
  - "SS_RIGHT 상수"
  - "SS_RIGHTJUST 상수"
  - "SS_SIMPLE 상수"
  - "SS_SUNKEN 상수"
  - "SS_USERITEM 상수"
  - "SS_WHITEFRAME 상수"
  - "SS_WHITERECT 상수"
  - "SS_WORDELLIPSIS 상수"
  - "정적 스타일"
ms.assetid: a1114548-fc6d-491d-8c46-21d11b8574f5
caps.latest.revision: 12
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 정적 스타일
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

-   **SS\_BITMAP** Specifies a bitmap is to be displayed in the static control.  The given text is the name of a bitmap \(not a filename\) defined elsewhere in the resource file.  The style ignores the nWidth and nHeight parameters; the control automatically sizes itself to accommodate the bitmap.  
  
-   **SS\_BLACKFRAME** Specifies a box with a frame drawn with the same color as window frames.  기본값은 검정입니다.  
  
-   **SS\_BLACKRECT** Specifies a rectangle filled with the color used to draw window frames.  기본값은 검정입니다.  
  
-   **SS\_CENTER** Designates a simple rectangle and displays the given text centered in the rectangle.  The text is formatted before it is displayed.  Words that would extend past the end of a line are automatically wrapped to the beginning of the next centered line.  
  
-   **SS\_CENTERIMAGE** Specifies that, if the bitmap or icon is smaller than the client area of the static control, the rest of the client area is filled with the color of the pixel in the top left corner of the bitmap or icon.  If the static control contains a single line of text, the text is centered vertically in the client area of the control.  
  
-   **SS\_ENDELLIPSIS** or **SS\_PATHELLIPSIS** Replaces part of the given string with ellipses, if necessary, so that the result fits in the specified rectangle.  
  
     You can specify **SS\_END\_ELLIPSIS** to replace characters at the end of the string, or **SS\_PATHELLIPSIS** to replace characters in the middle of the string.  If the string contains backslash \(\\\) characters, **SS\_PATHELLIPSIS** preserves as much of the text after the last backslash as possible.  
  
-   **SS\_ENHMETAFILE** Specifies an enhanced metafile is to be displayed in the static control.  The given text is the name of a metafile.  An enhanced metafile static control has a fixed size; the metafile is scaled to fit the static control's client area.  
  
-   **SS\_ETCHEDFRAME** Draws the frame of the static control using the **EDGE\_ETCHED** edge style.  
  
-   **SS\_ETCHEDHORZ** Draws the top and bottom edges of the static control using the **EDGE\_ETCHED** edge style.  
  
-   **SS\_ETCHEDVERT** Draws the left and right edges of the static control using the EDGE\_ETCHED edge style.  
  
-   **SS\_GRAYFRAME** Specifies a box with a frame drawn with the same color as the screen background \(desktop\).  기본값은 회색입니다.  
  
-   **SS\_GRAYRECT** Specifies a rectangle filled with the color used to fill the screen background.  기본값은 회색입니다.  
  
-   **SS\_ICON** Designates an icon displayed in the dialog box.  The given text is the name of an icon \(not a filename\) defined elsewhere in the resource file.  The `nWidth` and `nHeight` parameters are ignored; the icon automatically sizes itself.  
  
-   **SS\_LEFT** Designates a simple rectangle and displays the given text flush\-left in the rectangle.  The text is formatted before it is displayed.  Words that would extend past the end of a line are automatically wrapped to the beginning of the next flush\-left line.  
  
-   **SS\_LEFTNOWORDWRAP** Designates a simple rectangle and displays the given text flush\-left in the rectangle.  Tabs are expanded, but words are not wrapped.  Text that extends past the end of a line is clipped.  
  
-   **SS\_NOPREFIX** Unless this style is specified, Windows will interpret any ampersand \(&\) characters in the control's text to be accelerator prefix characters.  In this case, the ampersand is removed and the next character in the string is underlined.  If a static control is to contain text where this feature is not wanted, **SS\_NOPREFIX** may be added.  This static\-control style may be included with any of the defined static controls.  You can combine **SS\_NOPREFIX** with other styles by using the bitwise OR operator.  This is most often used when filenames or other strings that may contain an ampersand need to be displayed in a static control in a dialog box.  
  
-   **SS\_NOTIFY** Sends the parent window **STN\_CLICKED**, **STN\_DBLCLK**, **STN\_DISABLE**, and **STN\_ENABLE** notification messages when the user clicks or double\-clicks the control.  
  
-   **SS\_OWNERDRAW** Specifies that the owner of the static control is responsible for drawing the control.  The owner window receives a `WM_DRAWITEM` message whenever the control needs to be drawn.  
  
-   **SS\_REALSIZEIMAGE** Prevents a static icon or bitmap control \(that is, static controls that have the **SS\_ICON** or **SS\_BITMAP** style\) from being resized as it is loaded or drawn.  If the icon or bitmap is larger than the destination area, the image is clipped.  
  
-   **SS\_RIGHT** Designates a simple rectangle and displays the given text flush\-right in the rectangle.  The text is formatted before it is displayed.  Words that would extend past the end of a line are automatically wrapped to the beginning of the next flush\-right line.  
  
-   **SS\_RIGHTJUST** Specifies that the lower right corner of a static control with the **SS\_BITMAP** or **SS\_ICON** style is to remain fixed when the control is resized.  Only the top and left sides are adjusted to accommodate a new bitmap or icon.  
  
-   **SS\_SIMPLE** Designates a simple rectangle and displays a single line of text flush\-left in the rectangle.  The line of text cannot be shortened or altered in any way. \(The control's parent window or dialog box must not process the `WM_CTLCOLOR` message.\)  
  
-   **SS\_SUNKEN** Draws a half\-sunken border around a static control.  
  
-   **SS\_USERITEM** Specifies a user\-defined item.  
  
-   **SS\_WHITEFRAME** Specifies a box with a frame drawn with the same color as the window background.  기본값은 흰색입니다.  
  
-   **SS\_WHITERECT** Specifies a rectangle filled with the color used to fill the window background.  기본값은 흰색입니다.  
  
-   **SS\_WORDELLIPSIS** Truncates text that does not fit and adds ellipses.  
  
## 참고 항목  
 [MFC에서 사용하는 스타일](../../mfc/reference/styles-used-by-mfc.md)   
 [CStatic::Create](../Topic/CStatic::Create.md)   
 [DrawEdge](http://msdn.microsoft.com/library/windows/desktop/dd162477)   
 [Static Control Styles](http://msdn.microsoft.com/library/windows/desktop/bb760773)