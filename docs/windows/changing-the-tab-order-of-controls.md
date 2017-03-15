---
title: "Changing the Tab Order of Controls | Microsoft Docs"
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
  - "controls [C++], tab order"
  - "focus, tab order"
  - "tab controls, tab order"
  - "Tabstop property for controls"
  - "controls [C++], focus"
  - "dialog box controls, tab order"
ms.assetid: e2cee764-4367-42d7-9563-65a68f76f5ff
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Changing the Tab Order of Controls
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

탭 순서는 Tab 키를 눌렀을 때 대화 상자의 한 컨트롤에서 다음 컨트롤로 입력 포커스가 이동하는 순서입니다.  일반적으로 대화 상자에서 탭 순서는 왼쪽에서 오른쪽으로, 위쪽에서 아래쪽으로 진행됩니다.  각 컨트롤에는 입력 포커스를 받을 것인지 결정하는 **Tabstop** 속성이 있습니다.  
  
### 컨트롤에 입력 포커스를 설정하려면  
  
1.  [속성 창](../Topic/Properties%20Window.md)의 **Tabstop** 속성에서 **True** 또는 **False**를 선택합니다.  
  
 Tabstop 속성이 True로 설정되지 않은 컨트롤도 탭 순서에 포함되어야 합니다.  이것은 캡션이 없는 컨트롤에 대해 [니모닉\(선택키\)을 정의](../mfc/defining-mnemonics-access-keys.md)할 경우에 중요할 수 있습니다.  관련 컨트롤에 대한 선택키가 포함된 정적 텍스트는 탭 순서에서 관련 컨트롤 바로 앞에 와야 합니다.  
  
> [!NOTE]
>  대화 상자에 겹치는 컨트롤이 있을 경우에 탭 순서를 변경하면 컨트롤 표시 방법이 변경될 수도 있습니다.  탭 순서가 뒤쪽인 컨트롤은 항상 탭 순서가 앞인 겹치는 컨트롤 위에 표시됩니다.  
  
#### 대화 상자에서 모든 컨트롤의 현재 탭 순서를 보려면  
  
1.  **서식** 메뉴에서 **탭 순서**를 선택합니다.  
  
 \-또는\-  
  
-   Ctrl\+D를 누릅니다.  
  
#### 대화 상자에서 모든 컨트롤의 탭 순서를 변경하려면  
  
1.  **서식** 메뉴에서 **탭 순서**를 선택합니다.  
  
     그러면 각 컨트롤의 왼쪽 위 모퉁이에 현재 탭 순서가 숫자로 표시됩니다.  
  
2.  Tab 키를 눌렀을 때 이동할 순서대로 각 컨트롤을 클릭하여 탭 순서를 설정합니다.  
  
3.  **Enter** 키를 눌러 **탭 순서** 모드를 종료합니다.  
  
    > [!TIP]
    >  탭 순서 모드에서 Esc 키나 Enter 키를 누르면 탭 순서 변경 기능을 비활성화할 수 있습니다.  
  
#### 두 개 이상의 컨트롤에 대한 탭 순서를 변경하려면  
  
1.  **서식** 메뉴에서 **탭 순서**를 선택합니다.  
  
2.  순서 변경을 시작할 위치를 지정합니다.  위치를 지정하려면 **Ctrl** 키를 누른 채로 변경된 순서를 시작할 위치 앞의 컨트롤을 클릭합니다.  
  
     예를 들어, 7부터 9 컨트롤의 순서를 변경하려면 Ctrl 키를 누른 채로 6 컨트롤을 먼저 선택합니다.  
  
    > [!NOTE]
    >  특정 컨트롤을 숫자 1\(탭 순서에서 첫 번째\)로 설정하려면 해당 컨트롤을 두 번 클릭합니다.  
  
3.  Ctrl 키를 놓고 Tab 키에 따라 이동할 순서대로 컨트롤을 클릭합니다.  
  
4.  **Enter** 키를 눌러 **탭 순서** 모드를 종료합니다.  
  
 관리되는 프로젝트에 리소스를 추가하는 방법은 .NET Framework 개발자 가이드의 [응용 프로그램의 리소스](../Topic/Resources%20in%20Desktop%20Apps.md)를 참조하십시오. 관리되는 프로젝트에 리소스 파일 추가, 리소스 액세스, 정적 리소스 표시, 속성에 리소스 문자열 할당 등의 작업을 수동으로 수행하는 방법에 대한 자세한 내용은 [연습: Windows Forms 지역화](http://msdn.microsoft.com/ko-kr/9a96220d-a19b-4de0-9f48-01e5d82679e5) 및 [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)을 참조하십시오.  
  
### 요구 사항  
 Win32  
  
## 참고 항목  
 [Arrangement of Controls on Dialog Boxes](../mfc/arrangement-of-controls-on-dialog-boxes.md)   
 [Controls in Dialog Boxes](../mfc/controls-in-dialog-boxes.md)   
 [컨트롤](../mfc/controls-mfc.md)