---
title: "Controls in Dialog Boxes | Microsoft Docs"
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
  - "controls [C++], dialog boxes"
  - "dialog box controls, about dialog box controls"
  - "dialog box controls"
ms.assetid: e216c4f9-2fd4-429d-889a-8ebce7bad177
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Controls in Dialog Boxes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[도구 상자 창](../Topic/Toolbox.md)의 [대화 상자 편집기 탭](../mfc/dialog-editor-tab-toolbox.md)을 사용하면 대화 상자에 컨트롤을 추가할 수 있습니다. 즉, 원하는 컨트롤을 선택하여 대화 상자로 끌어 올 수 있습니다.  기본적으로, 도구 상자 창은 자동 숨기기로 설정됩니다.  따라서 대화 상자 편집기를 열 때 이것은 솔루션의 왼쪽 여백에 탭으로 표시됩니다.  그러나 창의 오른쪽 위 모퉁이에 있는 **자동 숨기기** 단추를 클릭하면 도구 상자 창의 위치를 고정할 수 있습니다.  이 창의 동작을 제어하는 방법에 대한 자세한 내용은 [창 관리](../Topic/Customizing%20window%20layouts%20in%20Visual%20Studio.md)를 참조하십시오.  
  
 대화 상자에 컨트롤 추가, 기존 컨트롤 위치 변경, 대화 상자 간의 컨트롤 이동 등의 작업을 가장 빨리 수행하려면 끌어서 놓기 방법을 사용하도록 합니다.  컨트롤을 대화 상자에 놓기 전까지는 컨트롤의 위치를 나타내는 윤곽선이 점선으로 표시됩니다.  끌어서 놓기 방법으로 대화 상자에 컨트롤을 추가하면 해당 컨트롤 형식에 맞는 표준 높이가 컨트롤에 지정됩니다.  
  
 대화 상자에 컨트롤을 추가하거나 컨트롤의 위치를 변경할 때 컨트롤의 최종 위치는 안내선이나 여백 또는 레이아웃 모눈 표시 여부에 따라 결정됩니다.  
  
 대화 상자에 컨트롤을 추가하고 나면 [속성 창](../Topic/Properties%20Window.md)에서 컨트롤의 Caption과 같은 속성을 변경할 수 있습니다.  여러 개의 컨트롤을 선택하여 동시에 속성을 변경할 수도 있습니다.  
  
-   [컨트롤 추가, 편집 및 삭제](../mfc/adding-editing-or-deleting-controls.md)  
  
-   [컨트롤 선택](../mfc/selecting-controls.md)  
  
-   [각 컨트롤 크기 조정](../mfc/sizing-individual-controls.md)  
  
-   [컨트롤의 너비, 높이, 크기를 동일하게 만들기](../mfc/making-controls-the-same-width-height-or-size.md)  
  
-   [콤보 상자 및 드롭다운 목록의 크기 설정](../mfc/setting-the-size-of-the-combo-box-and-its-drop-down-list.md)  
  
-   [콤보 상자 컨트롤에 값 추가](../mfc/adding-values-to-a-combo-box-control.md)  
  
-   [가로 스크롤 막대 너비 설정](../mfc/setting-the-width-of-a-horizontal-scroll-bar.md)  
  
-   [대화 상자에 컨트롤 배치](../mfc/arrangement-of-controls-on-dialog-boxes.md)  
  
-   [대화 상자 편집기의 사용자 지정 컨트롤](../mfc/custom-controls-in-the-dialog-editor.md)  
  
-   [니모닉\(선택키\) 정의](../mfc/defining-mnemonics-access-keys.md)  
  
-   [대화 상자의 위치와 크기 지정](../mfc/specifying-the-location-and-size-of-a-dialog-box.md)  
  
 관리되는 프로젝트에 리소스를 추가하는 방법은 .NET Framework 개발자 가이드의 [응용 프로그램의 리소스](../Topic/Resources%20in%20Desktop%20Apps.md)를 참조하십시오. 관리되는 프로젝트에 리소스 파일 추가, 리소스 액세스, 정적 리소스 표시, 속성에 리소스 문자열 할당 등의 작업을 수동으로 수행하는 방법에 대한 자세한 내용은 [연습: Windows Forms 지역화](http://msdn.microsoft.com/ko-kr/9a96220d-a19b-4de0-9f48-01e5d82679e5) 및 [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)을 참조하십시오.  
  
## 요구 사항  
 Win32  
  
## 참고 항목  
 [Adding Event Handlers for Dialog Box Controls](../mfc/adding-event-handlers-for-dialog-box-controls.md)   
 [대화 상자 컨트롤 및 변수 형식](../ide/dialog-box-controls-and-variable-types.md)   
 [Dialog Editor](../mfc/dialog-editor.md)