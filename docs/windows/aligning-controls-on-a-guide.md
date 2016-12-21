---
title: "Aligning Controls on a Guide | Microsoft Docs"
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
  - "DLUs (dialog units)"
  - "controls [C++], aligning"
  - "Dialog editor, snap to guides"
  - "guides, tick mark interval"
  - "dialog box controls, placement"
  - "guides, aligning controls"
  - "dialog units (DLUs)"
  - "snap to guides (Dialog editor)"
  - "controls [C++], sizing"
  - "tick mark interval in Dialog editor"
  - "controls [C++], snap to guides/grid"
ms.assetid: 17db84ba-5288-4478-be57-afa748aa6447
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Aligning Controls on a Guide
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

컨트롤을 이동하면 컨트롤 크기 조정 핸들이 안내선에 맞춰지고, 이전에 컨트롤을 안내선에 맞추지 않았으면 안내선이 컨트롤에 맞춰집니다.  안내선을 이동하면 여기에 맞춘 컨트롤도 이동합니다.  둘 이상의 안내선에 맞춰진 컨트롤은 안내선 중 하나를 이동하면 크기가 조정됩니다.  
  
 안내선과 컨트롤의 간격을 결정하는 눈금자의 눈금은 DLU\(대화 상자 단위\)로 정의됩니다.  DLU는 대화 상자 글꼴 크기\(일반적으로 8포인트 MS Shell Dlg\)를 기준으로 합니다.  가로 DLU는 대화 상자 글꼴의 평균 너비를 4로 나눈 것입니다.  세로 DLU는 글꼴의 평균 높이를 8로 나눈 것입니다.  
  
### 안내선으로 컨트롤 그룹의 크기를 조정하려면  
  
1.  하나 또는 여러 컨트롤의 한 쪽 면을 안내선에 맞춥니다.  
  
2.  하나 또는 여러 컨트롤의 다른 쪽 면으로 안내선을 끕니다.  
  
     여러 개의 컨트롤 크기를 조정하려면 두 번째 안내선에 맞춰 각 컨트롤의 크기를 조정합니다.  
  
3.  안내선을 이동하여 하나 또는 여러 컨트롤의 크기를 조정합니다.  
  
### 눈금 간격을 변경하려면  
  
1.  **서식** 메뉴에서 **안내선 설정**을 선택합니다.  
  
2.  [안내선 설정 대화 상자](../mfc/guide-settings-dialog-box.md)의 **모눈 간격** 필드에서 새 너비와 높이를 DLU 단위로 지정합니다.  
  
 관리되는 프로젝트에 리소스를 추가하는 방법은 .NET Framework 개발자 가이드의 [응용 프로그램의 리소스](../Topic/Resources%20in%20Desktop%20Apps.md)를 참조하십시오. 관리되는 프로젝트에 리소스 파일 추가, 리소스 액세스, 정적 리소스 표시, 속성에 리소스 문자열 할당 등의 작업을 수동으로 수행하는 방법에 대한 자세한 내용은 [연습: Windows Forms 지역화](http://msdn.microsoft.com/ko-kr/9a96220d-a19b-4de0-9f48-01e5d82679e5) 및 [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)을 참조하십시오.  
  
 요구 사항  
  
 Win32  
  
## 참고 항목  
 [Dialog Editor States \(Guides and Grids\)](../mfc/dialog-editor-states-guides-and-grids.md)   
 [Controls in Dialog Boxes](../mfc/controls-in-dialog-boxes.md)