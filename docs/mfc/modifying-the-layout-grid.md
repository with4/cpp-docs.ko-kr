---
title: "Modifying the Layout Grid | Microsoft Docs"
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
  - "C++"
helpviewer_keywords: 
  - "controls [C++], layout grid"
  - "snap to layout grid"
  - "grids, turning on or off"
  - "layout grid in Dialog Editor"
  - "grids, changing size"
ms.assetid: ec31f595-7542-485b-806f-efbaeccc1b3d
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Modifying the Layout Grid
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

대화 상자에서 컨트롤을 놓거나 배치할 때 레이아웃 모눈을 사용하면 정확한 위치를 지정할 수 있습니다.  모눈이 표시되어 있으면 컨트롤이 자석처럼 모눈의 점선에 "맞춰져" 표시됩니다.  이러한 "모눈에 맞춤" 기능을 활성화하거나 비활성화할 수 있으며 레이아웃 모눈 셀의 크기를 변경할 수 있습니다.  
  
### 레이아웃 모눈을 표시하거나 감추려면  
  
1.  **서식** 메뉴에서 **안내선 설정**을 선택합니다.  
  
2.  [안내선 설정 대화 상자](../mfc/guide-settings-dialog-box.md)에서 **모눈** 단추를 선택하거나 취소합니다.  
  
     각 대화 상자 편집기 창에서 [대화 상자 편집기 도구 모음](../mfc/showing-or-hiding-the-dialog-editor-toolbar.md)의 **모눈 설정\/해제** 단추를 사용하여 모눈을 제어할 수도 있습니다.  
  
### 레이아웃 모눈의 크기를 변경하려면  
  
1.  **서식** 메뉴에서 **안내선 설정**을 선택합니다.  
  
2.  [안내선 설정 대화 상자](../mfc/guide-settings-dialog-box.md)에서 모눈의 셀 높이와 너비를 DLU 단위로 입력합니다.  최소 높이나 너비는 4 DLU입니다.  DLU에 대한 자세한 내용은 [대화 상자에 컨트롤 배치](../mfc/arrangement-of-controls-on-dialog-boxes.md)를 참조하십시오.  
  
 관리되는 프로젝트에 리소스를 추가하는 방법은 .NET Framework 개발자 가이드의 [응용 프로그램의 리소스](../Topic/Resources%20in%20Desktop%20Apps.md)를 참조하십시오. 관리되는 프로젝트에 리소스 파일 추가, 리소스 액세스, 정적 리소스 표시, 속성에 리소스 문자열 할당 등의 작업을 수동으로 수행하는 방법에 대한 자세한 내용은 [연습: Windows Forms 지역화](http://msdn.microsoft.com/ko-kr/9a96220d-a19b-4de0-9f48-01e5d82679e5) 및 [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)을 참조하십시오.  
  
 요구 사항  
  
 Win32  
  
## 참고 항목  
 [Dialog Editor States \(Guides and Grids\)](../mfc/dialog-editor-states-guides-and-grids.md)   
 [Controls in Dialog Boxes](../mfc/controls-in-dialog-boxes.md)