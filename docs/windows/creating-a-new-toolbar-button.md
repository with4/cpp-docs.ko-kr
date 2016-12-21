---
title: "Creating a New Toolbar Button | Microsoft Docs"
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
  - "vc.editors.toolbar"
dev_langs: 
  - "C++"
  - "C++"
helpviewer_keywords: 
  - "Toolbar editor, creating buttons"
  - "toolbar buttons (in Toolbar editor), button image"
  - "toolbar buttons (in Toolbar editor), creating"
  - "toolbar buttons (in Toolbar editor)"
ms.assetid: 46c120fe-4f2a-4887-a08f-bd1fea04b3f4
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Creating a New Toolbar Button
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

### 새 도구 모음 단추를 만들려면  
  
1.  [리소스 뷰](../windows/resource-view-window.md)에서 리소스 폴더\(예: Project1.rc\)를 확장합니다.  
  
    > [!NOTE]
    >  프로젝트에 .rc 파일이 없으면 [새 리소스 스크립트 파일 만들기](../windows/how-to-create-a-resource-script-file.md)를 참조하십시오.  
  
2.  **도구 모음** 폴더를 확장하고 편집할 도구 모음을 선택합니다.  
  
3.  도구 모음 오른쪽 끝에 있는 빈 단추에 ID를 지정합니다.  [속성 창](../Topic/Properties%20Window.md)에서 **ID** 속성을 편집하여 ID를 지정할 수 있습니다.  예를 들어, 도구 모음 단추에 메뉴 옵션과 동일한 ID를 지정할 수 있습니다.  이 경우에는 드롭다운 목록 상자에서 메뉴 옵션의 **ID**를 선택하십시오.  
  
     – 또는 –  
  
     도구 모음 뷰 창에서 도구 모음 오른쪽 끝에 있는 빈 단추를 선택하고 그리기를 시작합니다.  기본 단추 명령 ID\(ID\_BUTTON\<n\>\)가 지정됩니다.  
  
 또한, 이미지를 복사하여 도구 모음에 새 단추로 붙여 넣을 수 있습니다.  
  
#### 이미지를 도구 모음에 단추로 추가하려면  
  
1.  [리소스 뷰](../windows/resource-view-window.md)에서 도구 모음을 두 번 클릭하여 엽니다.  
  
2.  그런 다음, 도구 모음에 추가할 이미지를 엽니다.  
  
    > [!NOTE]
    >  Visual Studio에서 이미지를 열면 이미지 편집기에 이미지가 열립니다.  다른 그래픽 프로그램을 사용하여 이미지를 열 수도 있습니다.  
  
3.  **편집** 메뉴에서 **복사**를 선택합니다.  
  
4.  소스 창 맨 위에 있는 탭을 클릭하여 도구 모음으로 전환합니다.  
  
5.  **편집** 메뉴에서 **붙여넣기**를 선택합니다.  
  
     이미지가 도구 모음에 새 단추로 표시됩니다.  
  
 관리되는 프로젝트에 리소스를 추가하는 방법은 .NET Framework 개발자 가이드의 [응용 프로그램의 리소스](../Topic/Resources%20in%20Desktop%20Apps.md)를 참조하십시오. 관리되는 프로젝트에 리소스 파일 추가, 리소스 액세스, 정적 리소스 표시, 속성에 리소스 문자열 할당 등의 작업을 수동으로 수행하는 방법에 대한 자세한 내용은 [연습: Windows Forms 지역화](http://msdn.microsoft.com/ko-kr/9a96220d-a19b-4de0-9f48-01e5d82679e5) 및 [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)을 참조하십시오.  
  
### 요구 사항  
 MFC 또는 ATL  
  
## 참고 항목  
 [Toolbar Button Properties](../mfc/toolbar-button-properties.md)   
 [Creating, Moving, and Editing Toolbar Buttons](../mfc/creating-moving-and-editing-toolbar-buttons.md)   
 [Toolbar Editor](../mfc/toolbar-editor.md)