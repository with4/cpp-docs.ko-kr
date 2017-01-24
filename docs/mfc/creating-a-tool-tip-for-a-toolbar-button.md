---
title: "Creating a Tool Tip for a Toolbar Button | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "tool tips [C++], adding to toolbar buttons"
  - "\n in tool tip"
  - "toolbar buttons [C++], tool tips"
  - "buttons [C++], tool tips"
  - "Toolbar editor, creating tool tips"
ms.assetid: 0af65342-fd78-4e78-8d0d-dc68f7fc462e
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Creating a Tool Tip for a Toolbar Button
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

### 도구 설명을 만들려면  
  
1.  도구 모음 단추를 선택합니다.  
  
2.  [속성 창](../Topic/Properties%20Window.md)의 **Prompt** 속성 필드에서 상태 표시줄에 표시할 단추에 대한 설명을 추가하고, 메시지 뒤에 \\n과 도구 설명 이름을 추가합니다.  
  
 일반적인 도구 설명의 예로는 워드패드의 인쇄 단추에 대한 도구 설명이 있습니다.  
  
 1.  워드패드를 엽니다.  
  
 2.  마우스 포인터로 **인쇄** 도구 모음 단추를 가리킵니다.  
  
 3.  마우스 포인터 아래에 '인쇄'라는 단어가 표시되는지 확인합니다.  
  
 4.  워드패드 창의 맨 아래에 있는 상태 표시줄에 "활성 문서를 인쇄합니다."라는 텍스트가 표시되는지 확인합니다.  
  
 3단계에서 '인쇄'라는 단어는 "도구 설명 이름"이고 4단계에서 '활성 문서를 인쇄합니다'라는 텍스트는 "상태 표시줄에 표시되는 단추에 대한 설명"입니다.  
  
 **도구 모음** 편집기에서 이러한 결과를 얻으려면 **Prompt** 속성을 **활성 문서를 인쇄합니다.\\n인쇄**로 설정하십시오.  
  
> [!NOTE]
>  [속성 창](../Topic/Properties%20Window.md)을 사용하여 프롬프트 텍스트를 편집할 수 있습니다.  
  
 관리되는 프로젝트에 리소스를 추가하는 방법은 .NET Framework 개발자 가이드의 [응용 프로그램의 리소스](../Topic/Resources%20in%20Desktop%20Apps.md)를 참조하십시오. 관리되는 프로젝트에 리소스 파일 추가, 리소스 액세스, 정적 리소스 표시, 속성에 리소스 문자열 할당 등의 작업을 수동으로 수행하는 방법에 대한 자세한 내용은 [연습: Windows Forms 지역화](http://msdn.microsoft.com/ko-kr/9a96220d-a19b-4de0-9f48-01e5d82679e5) 및 [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)을 참조하십시오.  
  
 요구 사항  
  
 MFC 또는 ATL  
  
## 참고 항목  
 [Creating, Moving, and Editing Toolbar Buttons](../mfc/creating-moving-and-editing-toolbar-buttons.md)   
 [Toolbar Editor](../mfc/toolbar-editor.md)