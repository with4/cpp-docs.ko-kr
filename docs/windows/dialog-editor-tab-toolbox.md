---
title: "도구 상자, 대화 상자 편집기 탭 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "도구 상자[C++], 대화 상자 편집기 탭"
  - "컨트롤[C++], 형식"
  - "대화 상자의 syslink 컨트롤"
  - "사용자 지정 컨트롤[Visual Studio], 대화 상자"
  - "컨트롤[C++], 표준"
  - "대화 상자 편집기, 컨트롤 만들기"
  - "컨트롤[C++], 대화 상자에 추가"
ms.assetid: 253885c2-dcb9-4d8e-ac9b-805ea31cbf5e
caps.latest.revision: 12
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 도구 상자, 대화 상자 편집기 탭
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

대화 상자 편집기에서 작업하는 경우 대화 상자 편집기 탭이 [도구 상자 창](../Topic/Toolbox.md)에 표시됩니다. 새 대화 상자에 컨트롤을 추가하려면 도구 상자에서 만들려는 대화 상자로 컨트롤을 끌어서 놓습니다\(자세한 내용은 [대화 상자에 컨트롤 추가](../mfc/adding-a-control-to-a-dialog-box.md) 참조\). 그런 다음 컨트롤을 주변으로 이동하거나 크기와 모양을 변경할 수 있습니다.  
  
 도구 상자에서 사용할 수 있는 표준 컨트롤은 다음과 같습니다.  
  
-   [Button 컨트롤](../mfc/reference/cbutton-class.md)  
  
-   [확인란 컨트롤](../mfc/reference/button-styles.md)  
  
-   [콤보 상자 컨트롤](../mfc/reference/ccombobox-class.md)  
  
-   [편집 컨트롤](../mfc/reference/cedit-class.md)  
  
-   그룹 상자  
  
-   [목록 상자 컨트롤](../mfc/reference/clistbox-class.md)  
  
-   [라디오 단추 컨트롤](../mfc/reference/button-styles.md)  
  
-   [정적 텍스트 컨트롤](../mfc/reference/cstatic-class.md)  
  
-   [그림 컨트롤](../mfc/reference/cpictureholder-class.md)  
  
-   [Rich Edit 2.0 컨트롤](../mfc/using-cricheditctrl.md)  
  
-   [스크롤 막대 컨트롤](../mfc/reference/cscrollbar-class.md)  
  
 도구 상자에서 사용할 수 있는 [Windows 공용 컨트롤](../mfc/controls-mfc.md)은 응용 프로그램에 향상된 기능을 제공합니다. 다음과 같은 변경 내용이 해당됩니다.  
  
-   [Slider 컨트롤](../mfc/slider-control-styles.md)  
  
-   [Spin 컨트롤](../mfc/using-cspinbuttonctrl.md)  
  
-   [Progress 컨트롤](../mfc/styles-for-the-progress-control.md)  
  
-   [Hot Key 컨트롤](../mfc/using-a-hot-key-control.md)  
  
-   [목록 컨트롤](../mfc/list-control-and-list-view.md)  
  
-   [트리 컨트롤](../mfc/tree-control-styles.md)  
  
-   [탭 컨트롤](../mfc/tab-controls-and-property-sheets.md)  
  
-   [애니메이션 컨트롤](../mfc/using-an-animation-control.md)  
  
-   [날짜 시간 선택 컨트롤](../mfc/creating-the-date-and-time-picker-control.md)  
  
-   [MonthCalendar 컨트롤](../mfc/month-calendar-control-examples.md)  
  
-   [IP 주소 컨트롤](../mfc/reference/cipaddressctrl-class.md)  
  
-   [확장된 콤보 상자 컨트롤](../mfc/creating-an-extended-combo-box-control.md)  
  
-   [사용자 지정 컨트롤](../mfc/custom-controls-in-the-dialog-editor.md)  
  
 도구 상자에서 **사용자 지정 컨트롤** 아이콘을 선택하여 대화 상자에 끌어서 놓아 대화 상자에 사용자 지정 컨트롤을 추가할 수 있습니다. Syslink 컨트롤을 추가하려면 사용자 지정 컨트롤을 추가한 후 컨트롤의 **Class** 속성을 **Syslink**로 변경합니다. 이렇게 하면 속성이 새로 고쳐지고 Syslink 컨트롤 속성이 표시됩니다. MFC 래퍼 클래스에 대한 자세한 내용은 [CLinkCtrl](../mfc/reference/clinkctrl-class.md)을 참조하세요.  
  
 또한 [대화 상자에 ActiveX 컨트롤을 추가](../mfc/viewing-and-adding-activex-controls-to-a-dialog-box.md)할 수도 있습니다.  
  
 더욱 쉽게 사용하기 위해 도구 상자 창을 사용자 지정할 수도 있습니다. 자세한 내용은 [도구 상자의 항목 및 탭 관리](http://msdn.microsoft.com/ko-kr/21285050-cadd-455a-b1f5-a2289a89c4db)를 참조하세요. 예를 들어 쉬운 액세스를 위해 도구 상자 창에 컨트롤을 배치할 수 있습니다. 자세한 내용은 [도구 상자 대화 상자 사용자 지정](http://msdn.microsoft.com/ko-kr/bd07835f-18a8-433e-bccc-7141f65263bb)을 참조하세요.  
  
 MFC에서 RichEdit 1.0 컨트롤을 사용하는 방법에 대한 자세한 내용은 [MFC에 RichEdit 1.0 컨트롤 사용](../mfc/using-the-richedit-1-0-control-with-mfc.md)을 참조하세요.  
  
 관리되는 프로젝트에 리소스를 추가하는 방법은 *.NET Framework 개발자 가이드*에서 [응용 프로그램의 리소스](../Topic/Resources%20in%20Desktop%20Apps.md)를 참조하세요. 관리되는 프로젝트에 리소스 파일 추가, 리소스 액세스, 정적 리소스 표시, 속성에 리소스 문자열 할당 등의 작업을 수동으로 수행하는 방법에 대한 자세한 내용은 [연습: Windows Forms 지역화](http://msdn.microsoft.com/ko-kr/9a96220d-a19b-4de0-9f48-01e5d82679e5) 및 [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)을 참조하세요.  
  
## 요구 사항  
 Win32  
  
## 참고 항목  
 [컨트롤](../mfc/controls-mfc.md)   
 [컨트롤 클래스](../mfc/control-classes.md)   
 [대화 상자 클래스](../mfc/dialog-box-classes.md)   
 [스크롤 막대 스타일](../mfc/reference/scroll-bar-styles.md)   
 [Rich Edit 컨트롤 예](../mfc/rich-edit-control-examples.md)   
 [Adding Event Handlers for Dialog Box Controls](../mfc/adding-event-handlers-for-dialog-box-controls.md)   
 [대화 상자 컨트롤 및 변수 형식](../ide/dialog-box-controls-and-variable-types.md)