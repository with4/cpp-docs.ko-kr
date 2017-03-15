---
title: "Converting Bitmaps to Toolbars | Microsoft Docs"
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
  - "bitmaps [C++], converting to toolbars"
  - "Toolbar editor, converting bitmaps"
  - "toolbars [C++], converting bitmaps"
ms.assetid: 971c181b-40f5-44be-843d-677a7c235667
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Converting Bitmaps to Toolbars
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

비트맵을 변환하여 새 도구 모음을 만들 수 있습니다.  그러면 비트맵의 그래픽이 도구 모음의 단추 이미지로 변환됩니다.  일반적으로 하나의 비트맵에는 여러 개의 단추 이미지가 포함되어 있고, 각 단추마다 이미지가 하나씩 있습니다.  이미지 크기는 조정할 수 있고, 기본 크기는 16 x 16 픽셀입니다.  이미지 편집기의 **이미지** 메뉴에서 도구 모음 편집기를 선택하면 [새 도구 모음 리소스 대화 상자](../mfc/new-toolbar-resource-dialog-box.md)에서 단추 이미지의 크기를 지정할 수 있습니다.  
  
### 비트맵을 도구 모음으로 변환하려면  
  
1.  [이미지 편집기](../mfc/image-editor-for-icons.md)에서 기존 비트맵 리소스를 엽니다.  .rc 파일에 비트맵이 없으면 마우스 오른쪽 단추로 .rc 파일을 클릭하고 바로 가기 메뉴에서 **가져오기**를 선택한 다음, .rc 파일에 추가할 비트맵을 찾아 **열기**를 클릭합니다.  
  
2.  **이미지** 메뉴에서 **도구 모음 편집기**를 선택합니다.  
  
     [새 도구 모음 리소스 대화 상자](../mfc/new-toolbar-resource-dialog-box.md)가 나타납니다.  비트맵에 맞게 아이콘 이미지의 너비와 높이를 변경할 수 있습니다.  그러면 도구 모음 편집기에 도구 모음 이미지가 표시됩니다.  
  
3.  변환을 끝내려면 [속성 창](../Topic/Properties%20Window.md)을 사용하여 단추의 명령 **ID**를 변경합니다.  새로운 **ID**를 입력하거나 드롭다운 목록에서 **ID**를 선택합니다.  
  
    > [!TIP]
    >  속성 창의 제목 표시줄에는 푸시핀 단추가 있습니다.  이 단추를 클릭하면 창에 대한 자동 숨기기가 설정되거나 해제됩니다.  각 속성 창을 다시 열지 않고 신속하게 도구 모음 단추 속성을 확인하려면 속성 창이 고정되도록 자동 숨기기를 해제하십시오.  
  
 [속성 창](../Topic/Properties%20Window.md)을 사용하여 새 도구 모음에 있는 단추의 명령 ID를 변경할 수도 있습니다.  새 도구 모음의 편집에 대한 자세한 내용은 [도구 모음 단추 만들기, 이동 및 편집](../mfc/creating-moving-and-editing-toolbar-buttons.md)을 참조하십시오.  
  
 관리되는 프로젝트에 리소스를 추가하는 방법은 .NET Framework 개발자 가이드의 [응용 프로그램의 리소스](../Topic/Resources%20in%20Desktop%20Apps.md)를 참조하십시오. 관리되는 프로젝트에 리소스 파일 추가, 리소스 액세스, 정적 리소스 표시, 속성에 리소스 문자열 할당 등의 작업을 수동으로 수행하는 방법에 대한 자세한 내용은 [연습: Windows Forms 지역화](http://msdn.microsoft.com/ko-kr/9a96220d-a19b-4de0-9f48-01e5d82679e5) 및 [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)을 참조하십시오.  
  
 요구 사항  
  
 MFC 또는 ATL  
  
## 참고 항목  
 [Creating New Toolbars](../mfc/creating-new-toolbars.md)   
 [Toolbar Editor](../mfc/toolbar-editor.md)