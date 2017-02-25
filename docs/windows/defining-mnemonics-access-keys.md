---
title: "Defining Mnemonics (Access Keys) | Microsoft Docs"
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
  - "access keys [C++], adding"
  - "keyboard shortcuts [C++], controls"
  - "dialog box controls, mnemonics"
  - "access keys [C++], checking"
  - "mnemonics, checking for duplicate"
  - "mnemonics"
  - "mnemonics, dialog box controls"
  - "keyboard shortcuts [C++], uniqueness checking"
  - "Check Mnemonics command"
  - "controls [C++], access keys"
  - "access keys [C++]"
ms.assetid: 60a85435-aa30-4c5c-98b6-42fb045b9eb2
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Defining Mnemonics (Access Keys)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

일반적으로 키보드 사용자는 대화 상자에서 Tab 키와 화살표 키를 사용하여 한 컨트롤에서 다른 컨트롤로 입력 포커스를 이동합니다.  그러나 선택키\(니모닉이나 기억하기 쉬운 이름\)를 정의하고 키 하나만 눌러 컨트롤을 선택할 수도 있습니다.  
  
### 보이는 캡션\(누름 단추, 확인란 및 라디오 단추\)을 사용하여 컨트롤의 선택키를 정의하려면  
  
1.  대화 상자에서 컨트롤을 선택합니다.  
  
2.  [속성 창](../Topic/Properties%20Window.md)의 **Caption** 속성에 컨트롤의 새 이름을 입력하고 컨트롤의 선택키로 사용할 문자 앞에 앰퍼샌드\(**&**\)를 입력합니다.  예를 들어, `&Radio1`을 입력합니다.  
  
3.  **Enter** 키를 누릅니다.  
  
     그러면 캡션에서 선택키를 나타내는 문자에 밑줄이 표시됩니다\(예: **R**adio1\).  
  
### 캡션을 표시하지 않고 컨트롤의 선택키를 정의하려면  
  
1.  [도구 상자](../Topic/Toolbox.md)에서 **Static Text** 컨트롤을 사용하여 컨트롤의 캡션을 만듭니다.  
  
2.  정적 텍스트 캡션에서 선택키로 사용할 문자 앞에 앰퍼샌드\(**&**\)를 입력합니다.  
  
3.  정적 텍스트 컨트롤은 탭 순서에서 레이블 표시가 된 컨트롤의 바로 앞에 와야 합니다.  
  
 대화 상자에 있는 모든 선택키는 고유해야 합니다.  
  
#### 중복된 선택키를 확인하려면  
  
1.  **서식** 메뉴에서 **니모닉 확인**을 선택합니다.  
  
 관리되는 프로젝트에 리소스를 추가하는 방법은 .NET Framework 개발자 가이드의 [응용 프로그램의 리소스](../Topic/Resources%20in%20Desktop%20Apps.md)를 참조하십시오. 관리되는 프로젝트에 리소스 파일 추가, 리소스 액세스, 정적 리소스 표시, 속성에 리소스 문자열 할당 등의 작업을 수동으로 수행하는 방법에 대한 자세한 내용은 [연습: Windows Forms 지역화](http://msdn.microsoft.com/ko-kr/9a96220d-a19b-4de0-9f48-01e5d82679e5) 및 [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)을 참조하십시오.  
  
### 요구 사항  
 Win32  
  
## 참고 항목  
 [Controls in Dialog Boxes](../mfc/controls-in-dialog-boxes.md)   
 [컨트롤](../mfc/controls-mfc.md)