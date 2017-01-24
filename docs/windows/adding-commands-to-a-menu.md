---
title: "Adding Commands to a Menu | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.menu"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "menu items, adding to menus"
  - "menus, adding items"
  - "commands, adding to menus"
  - "commands"
  - "menu items"
ms.assetid: 1523a755-0ab5-42f8-9e98-bb9881564431
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Adding Commands to a Menu
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

### 메뉴에 명령을 추가하려면  
  
1.  [메뉴를 만듭니다](../windows/creating-a-menu.md).  
  
2.  파일과 같은 메뉴 이름을 클릭합니다.  
  
     각 메뉴가 확장되고 명령에 대한 새 항목 상자가 표시됩니다.  예를 들어 새로 만들기, 열기 및 닫기와 같은 명령을 파일 메뉴에 추가할 수 있습니다.  
  
3.  새 항목 상자에 새 메뉴 명령에 대한 이름을 입력합니다.  
  
    > [!NOTE]
    >  입력하는 텍스트는 메뉴 편집기와 [속성 창](../Topic/Properties%20Window.md)의 **캡션** 상자에 모두 나타납니다.  한 위치에서 새 메뉴에 대한 속성을 편집할 수 있습니다.  
  
    > [!TIP]
    >  사용자가 메뉴 명령을 선택할 수 있도록 니모닉 키\(바로 가기 키\)를 정의할 수 있습니다.  니모닉으로 지정하려면 문자 앞에 앰퍼샌드\(&\)를 입력합니다.  사용자는 해당 문자를 입력하여 메뉴 명령을 선택할 수 있습니다.  
  
4.  속성 창에서 적용되는 메뉴 명령 속성을 선택합니다.  자세한 내용은 [메뉴 명령 속성](../windows/menu-command-properties.md)을 참조하세요.  
  
5.  속성 창의 **프롬프트** 상자에 응용 프로그램의 상태 표시줄에 표시할 프롬프트 문자열을 입력합니다.  
  
     이렇게 하면 앞에서 만든 메뉴 명령과 동일한 리소스 식별자를 사용하는 항목이 문자열 테이블에 만들어집니다.  
  
    > [!NOTE]
    >  프롬프트는 **팝업** 속성이 **True**인 메뉴 항목에만 적용할 수 있습니다.  예를 들어 최상위 메뉴 항목은 하위 메뉴 항목이 있는 경우 프롬프트가 적용됩니다.  프롬프트의 용도는 사용자가 메뉴 항목을 클릭할 경우 발생하는 동작을 나타내는 것입니다.  
  
6.  **Enter** 키를 눌러 메뉴 명령을 완료합니다.  
  
     새 항목 상자를 선택하여 추가 메뉴 명령을 만들 수 있습니다.  
  
 관리되는 프로젝트에 리소스를 추가하는 방법은 .NET Framework 개발자 가이드의 [응용 프로그램의 리소스](../Topic/Resources%20in%20Desktop%20Apps.md)를 참조하십시오. 관리되는 프로젝트에 리소스 파일 추가, 리소스 액세스, 정적 리소스 표시, 속성에 리소스 문자열 할당 등의 작업을 수동으로 수행하는 방법에 대한 자세한 내용은 [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)을 참조하세요.  
  
 **요구 사항**  
  
 Win32  
  
## 참고 항목  
 [Menu Editor](../mfc/menu-editor.md)   
 [메뉴](_win32_Menus)