---
title: "장치 컨텍스트 | Microsoft Docs"
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
  - "BeginPaint 메서드, CPaintDC"
  - "CClientDC 클래스, 및 GetDC 메서드"
  - "CClientDC 클래스, 및 ReleaseDC 메서드"
  - "CDC 클래스, 개체"
  - "클라이언트 영역"
  - "클라이언트 영역, 및 장치 컨텍스트"
  - "CMetaFileDC 클래스, 및 OnPrepareDC 메서드"
  - "CPaintDC 클래스, 그리기 장치 컨텍스트"
  - "장치 컨텍스트[C++]"
  - "장치 컨텍스트[C++], 장치 컨텍스트 정보"
  - "장치 컨텍스트[C++], CDC 클래스"
  - "장치 독립적 그리기"
  - "그리기, 장치 컨텍스트"
  - "그리기, 창에 직접"
  - "그리기, 마우스 및 장치 컨텍스트에서"
  - "EndPaint 메서드"
  - "프레임 창[C++], 장치 컨텍스트"
  - "GDI 개체[C++], 장치 컨텍스트"
  - "GetDC 메서드 및 CClientDC 클래스"
  - "그래픽 개체, 장치 컨텍스트"
  - "메타파일 및 장치 컨텍스트"
  - "마우스[C++], 그리기 및 장치 컨텍스트"
  - "OnPrepareDC 메서드"
  - "그리기 및 장치 컨텍스트"
  - "프린터[C++], 장치 컨텍스트"
  - "ReleaseDC 메서드"
  - "사용자 인터페이스[C++], 장치 컨텍스트"
  - "창[C++], 및 장치 컨텍스트"
  - "창[C++], 직접 그리기"
ms.assetid: d0cd51f1-f778-4c7e-bf50-d738d10433c7
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# 장치 컨텍스트
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

A device context is a Windows data structure containing information about the drawing attributes of a device such as a display or a printer.  All drawing calls are made through a device\-context object, which encapsulates the Windows APIs for drawing lines, shapes, and text.  Device contexts allow device\-independent drawing in Windows.  Device contexts can be used to draw to the screen, to the printer, or to a metafile.  
  
 [CPaintDC](../mfc/reference/cpaintdc-class.md) objects encapsulate the common idiom of Windows, calling the `BeginPaint` function, then drawing in the device context, then calling the `EndPaint` function.  The `CPaintDC` constructor calls `BeginPaint` for you, and the destructor calls `EndPaint`.  The simplified process is to create the [CDC](../mfc/reference/cdc-class.md) object, draw, and then destroy the `CDC` object.  In the framework, much of even this process is automated.  In particular, your `OnDraw` function is passed a `CPaintDC` already prepared \(via `OnPrepareDC`\), and you simply draw into it.  It is destroyed by the framework and the underlying device context is released to Windows upon return from the call to your `OnDraw` function.  
  
 [CClientDC](../mfc/reference/cclientdc-class.md) objects encapsulate working with a device context that represents only the client area of a window.  The `CClientDC` constructor calls the `GetDC` function, and the destructor calls the `ReleaseDC` function.  [CWindowDC](../mfc/reference/cwindowdc-class.md) objects encapsulate a device context that represents the whole window, including its frame.  
  
 [CMetaFileDC](../mfc/reference/cmetafiledc-class.md) objects encapsulate drawing into a Windows metafile.  In contrast to the `CPaintDC` passed to `OnDraw`, you must in this case call [OnPrepareDC](../Topic/CView::OnPrepareDC.md) yourself.  
  
## Mouse Drawing  
 Most drawing in a framework program — and thus most device\-context work — is done in the view's `OnDraw` member function.  However, you can still use device\-context objects for other purposes.  For example, to provide tracking feedback for mouse movement in a view, you need to draw directly into the view without waiting for `OnDraw` to be called.  
  
 In such a case, you can use a [CClientDC](../mfc/reference/cclientdc-class.md) device\-context object to draw directly into the view.  
  
### 추가 정보  
  
-   [\<caps:sentence id\="tgt22" sentenceid\="a12b51e88715aef1e34dc9b8f4447117" class\="tgtSentence"\>Device contexts \(definition\)\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/dd183553)  
  
-   [Drawing in a View](../mfc/drawing-in-a-view.md)  
  
-   [Interpreting User Input Through a View](../mfc/interpreting-user-input-through-a-view.md)  
  
-   [\<caps:sentence id\="tgt25" sentenceid\="f3dbb554cb14503827bf0ebda53953d7" class\="tgtSentence"\>Lines and curves\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/dd145028)  
  
-   [\<caps:sentence id\="tgt26" sentenceid\="365f749101c5eabc8b3be48de1dc3d6b" class\="tgtSentence"\>Filled shapes\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/dd162714)  
  
-   [\<caps:sentence id\="tgt27" sentenceid\="dc86a6302992c2d9f64d0fc6a8cfef75" class\="tgtSentence"\>Fonts and text\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/dd144819)  
  
-   [\<caps:sentence id\="tgt28" sentenceid\="62848e3ce5804aa985513a7922ff87b2" class\="tgtSentence"\>Colors\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/dd183450)  
  
-   [\<caps:sentence id\="tgt29" sentenceid\="ee85800dfcba9a5bdf11f101e1bbadeb" class\="tgtSentence"\>Coordinate spaces and transformations\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/dd183475)  
  
## 참고 항목  
 [창 개체](../mfc/window-objects.md)