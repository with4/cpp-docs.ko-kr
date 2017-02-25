---
title: "Assigning Access Keys to Menu Commands | Microsoft Docs"
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
  - "access keys [C++], checking"
  - "menus, shortcut keys"
  - "keyboard shortcuts [C++], command assignments"
  - "access keys [C++], assigning"
  - "mnemonics, adding to menus"
  - "keyboard shortcuts [C++], uniqueness checking"
  - "mnemonics, uniqueness checking"
  - "Check Mnemonics command"
ms.assetid: fbcf1a00-af6a-4171-805a-0ac01d4e8b0d
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Assigning Access Keys to Menu Commands
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

액세스 키\(사용자가 키보드로 메뉴를 선택할 수 있게 하는 니모닉\)를 메뉴 및 메뉴 명령에 할당할 수 있습니다.  
  
### 액세스\(바로 가기\) 키를 메뉴 명령에 할당하려면  
  
1.  메뉴 이름이나 명령 이름 앞에 앰퍼샌드\(**&**\)를 입력하여 이 문자를 해당 액세스 키로 지정합니다. 예를 들어 "&File"은 Microsoft Windows용으로 작성된 응용 프로그램에서 ALT\+F를 파일 메뉴의 바로 가기 키로 설정합니다.  
  
     메뉴 항목은 문자의 하나에 바로 가기 키가 할당되는 시각적 표시를 제공합니다. 앰퍼샌드 뒤의 문자에는 밑줄이 표시됩니다\(운영 체제에 따라\).  
  
    > [!NOTE]
    >  메뉴를 마우스 오른쪽 단추로 클릭하고 바로 가기 메뉴에서 **니모닉 확인**을 선택하여 메뉴의 모든 액세스 키가 고유한지 확인합니다.  
  
 관리되는 프로젝트에 리소스를 추가하는 방법은 *.NET Framework 개발자 가이드*에서 [응용 프로그램의 리소스](../Topic/Resources%20in%20Desktop%20Apps.md)를 참조하세요. 관리되는 프로젝트에 리소스 파일 추가, 리소스 액세스, 정적 리소스 표시, 속성에 리소스 문자열 할당 등의 작업을 수동으로 수행하는 방법에 대한 자세한 내용은 [연습: Windows Forms 지역화](http://msdn.microsoft.com/ko-kr/9a96220d-a19b-4de0-9f48-01e5d82679e5) 및 [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)을 참조하세요.  
  
 요구 사항  
  
 Win32  
  
## 참고 항목  
 [Menu Editor](../mfc/menu-editor.md)