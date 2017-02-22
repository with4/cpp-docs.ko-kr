---
title: "뷰 스크롤 및 크기 조정 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "메시지 처리기"
  - "메시지 처리, 뷰 클래스의 스크롤 막대"
  - "뷰 크기 조정"
  - "스크롤 막대, 메시지"
  - "뷰 스크롤"
ms.assetid: f98a3421-c336-407e-97ee-dbb2ffd76fbd
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# 뷰 스크롤 및 크기 조정
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC supports views that scroll and views that are automatically scaled to the size of the frame window that displays them.  Class `CScrollView` supports both kinds of views.  
  
 For more information about scrolling and scaling, see class [CScrollView](../mfc/reference/cscrollview-class.md) in the *MFC Reference*.  For a scrolling example, see the [Scribble sample](../top/visual-cpp-samples.md).  
  
## 추가 정보  
  
-   Scrolling a view  
  
-   Scaling a view  
  
-   [\<caps:sentence id\="tgt8" sentenceid\="f321fcf7c88bc6e3f892ae0fc9b2f0d8" class\="tgtSentence"\>View coordinates\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/dd145205)  
  
##  <a name="_core_scrolling_a_view"></a> Scrolling a View  
 Frequently the size of a document is greater than the size its view can display.  This may occur because the document's data increases or the user shrinks the window that frames the view.  In such cases, the view must support scrolling.  
  
 Any view can handle scroll\-bar messages in its `OnHScroll` and `OnVScroll` member functions.  You can either implement scroll\-bar message handling in these functions, doing all the work yourself, or you can use the `CScrollView` class to handle scrolling for you.  
  
 `CScrollView`에서는 다음과 같은 작업을 수행합니다.  
  
-   Manages window and viewport sizes and mapping modes  
  
-   Scrolls automatically in response to scroll\-bar messages  
  
 You can specify how much to scroll for a "page" \(when the user clicks in a scroll\-bar shaft\) and a "line" \(when the user clicks in a scroll arrow\).  Plan these values to suit the nature of your view.  For example, you might want to scroll in 1\-pixel increments for a graphics view but in increments based on the line height in text documents.  
  
##  <a name="_core_scaling_a_view"></a> Scaling a View  
 When you want the view to automatically fit the size of its frame window, you can use `CScrollView` for scaling instead of scrolling.  The logical view is stretched or shrunk to fit the window's client area exactly.  A scaled view has no scroll bars.  
  
## 참고 항목  
 [뷰 사용](../mfc/using-views.md)