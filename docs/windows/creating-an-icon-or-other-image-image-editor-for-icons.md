---
title: "Creating an Icon or Other Image (Image Editor for Icons) | Microsoft Docs"
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
  - "vc.editors.bitmap"
dev_langs: 
  - "C++"
  - "C++"
helpviewer_keywords: 
  - "bitmaps [C++]"
  - "images [C++], creating"
  - "resource toolbars"
  - "resources [Visual Studio], creating images"
  - "bitmaps [C++], creating"
  - "graphics [C++], creating"
  - "Image editor [C++], creating images"
ms.assetid: 66db3fb2-cfc1-48a2-9bdd-53f61eb7ee30
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Creating an Icon or Other Image (Image Editor for Icons)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

새 비트맵, 아이콘, 커서 및 도구 모음 이미지를 만들고 이미지 편집기를 사용하여 이미지의 모양을 사용자 지정할 수 있습니다.  또한 [템플릿](../windows/how-to-use-resource-templates.md)을 사용하여 새 비트맵을 만들 수도 있습니다.  
  
### 관리되지 않는 C\+\+ 프로젝트에 새 이미지 리소스를 추가하려면  
  
1.  [리소스 뷰](../windows/resource-view-window.md)에서 .rc 파일을 마우스 오른쪽 단추로 클릭하고 바로 가기 메뉴에서 **리소스 삽입**을 선택합니다.  .rc 파일에 커서 같은 기존 이미지 리소스가 있으면 **Cursor** 폴더를 마우스 오른쪽 단추로 클릭하고 바로 가기 메뉴에서 **Cursor  삽입**을 선택합니다.  
  
    > [!NOTE]
    >  **참고** 프로젝트에 .rc 파일이 없으면 [새 리소스 스크립트 파일 만들기](../windows/how-to-create-a-resource-script-file.md)를 참조하십시오.  
  
2.  [리소스 삽입 대화 상자](../windows/add-resource-dialog-box.md)에서 만들려고 하는 이미지 리소스의 형식\(예: **비트맵**\)을 선택한 다음 **새로 만들기**를 클릭합니다.  
  
     **리소스 삽입** 대화 상자의 이미지 리소스 종류 옆에 더하기 기호\(**\+**\)가 표시되면 도구 모음 템플릿을 사용할 수 있습니다.  더하기 기호\(\+\)를 클릭하여 템플릿 목록을 확장하고 템플릿을 선택한 다음 **새로 만들기**를 클릭합니다.  
  
### .NET 프로그래밍 언어에서 프로젝트에 새 이미지 리소스를 추가하려면  
  
1.  **솔루션 탐색기**에서 마우스 오른쪽 단추로 프로젝트 폴더\(예: **WindowsApplication1**\)를 클릭합니다.  
  
2.  바로 가기 메뉴에서 **추가**를 클릭하고 **새 항목 추가**를 선택합니다.  
  
3.  **범주** 창에서 **로컬 프로젝트 항목** 폴더를 확장한 다음 **리소스**를 선택합니다.  
  
4.  **템플릿** 창에서 프로젝트에 추가할 리소스 형식을 선택합니다.  
  
     솔루션 탐색기에서 리소스가 프로젝트에 추가되고 리소스가 [이미지 편집기](../mfc/image-editor-for-icons.md)에서 열립니다.  이미지 편집기에서 사용할 수 있는 모든 도구를 사용하여 이미지를 편집할 수 있습니다.  관리되는 프로젝트에 이미지 추가하는 방법은 [디자인 타임에서 그림 로드](../Topic/How%20to:%20Load%20a%20Picture%20Using%20the%20Designer%20\(Windows%20Forms\).md)를 참조하십시오.  
  
    > [!NOTE]
    >  편집할 관리되는 리소스는 연결된 리소스여야 합니다.  Visual Studio 리소스 편집기에서는 포함된 리소스를 편집할 수 없습니다.  자세한 내용은 *.NET Framework 개발자 가이드*의 [리소스 파일 만들기](../Topic/Creating%20Resource%20Files%20for%20Desktop%20Apps.md)를 참조하십시오.  
  
 관리되는 프로젝트에 리소스를 추가하는 방법은 .NET Framework 개발자 가이드의 [응용 프로그램의 리소스](../Topic/Resources%20in%20Desktop%20Apps.md)를 참조하십시오. 관리되는 프로젝트에 리소스 파일 추가, 리소스 액세스, 정적 리소스 표시, 속성에 리소스 문자열 할당 등의 작업을 수동으로 수행하는 방법에 대한 자세한 내용은 [연습: Windows Forms 지역화](http://msdn.microsoft.com/ko-kr/9a96220d-a19b-4de0-9f48-01e5d82679e5) 및 [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)을 참조하십시오.  
  
 요구 사항  
  
 없음  
  
## 참고 항목  
 [Icons and Cursors: Image Resources for Display Devices](../mfc/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)   
 [Converting Bitmaps to Toolbars](../mfc/converting-bitmaps-to-toolbars.md)   
 [Creating New Toolbars](../mfc/creating-new-toolbars.md)   
 [Editing Graphical Resources](../mfc/editing-graphical-resources-image-editor-for-icons.md)   
 [Image Editor for Icons](../mfc/image-editor-for-icons.md)