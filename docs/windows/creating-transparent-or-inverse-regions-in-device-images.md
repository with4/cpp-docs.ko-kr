---
title: "Creating Transparent or Inverse Regions in Device Images (Image Editor for Icons) | Microsoft Docs"
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
  - "C++"
helpviewer_keywords: 
  - "cursors [C++], screen regions"
  - "inverse colors, device images"
  - "transparent regions, device images"
  - "transparency, device images"
  - "Image editor [C++], device images"
  - "inverse regions, device images"
  - "cursors [C++], transparent regions"
  - "screen colors"
  - "regions, transparent"
  - "icons [C++], transparent regions"
  - "display devices, transparent and screen regions"
  - "transparent regions in devices"
  - "regions, inverse"
  - "colors [C++], Image editor"
  - "device projects, transparent images"
  - "icons [C++], screen regions"
ms.assetid: a994954b-b039-4391-a535-58d1fa10fc3b
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Creating Transparent or Inverse Regions in Device Images (Image Editor for Icons)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[이미지 편집기](../mfc/image-editor-for-icons.md)에서 만드는 초기 아이콘과 커서 이미지의 특성은 투명합니다.  아이콘과 커서 이미지는 사각형이지만 이미지의 일부가 투명하기 때문에 대부분은 사각으로 표시되지 않고 화면의 내부 이미지가 아이콘과 커서 위에 표시됩니다.  아이콘을 끌면 이미지의 일부가 반전된 색으로 표시될 수도 있습니다.  [색상 창](../windows/colors-window-image-editor-for-icons.md)에서 화면색과 반전색을 설정하면 이 효과를 만들 수 있습니다.  
  
 아이콘과 커서에 적용한 화면색과 반전색은 파생된 이미지의 모양과 색을 만들거나 반전 영역을 지정합니다  색은 이런 특성을 갖는 이미지의 일부를 나타냅니다.  편집할 때 화면색과 반전색 특성을 나타내는 색을 변경할 수 있습니다.  이렇게 변경해도 응용 프로그램의 아이콘이나 커서의 모양에 영향을 주지는 않습니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
### 투명한 영역이나 반전 영역을 만들려면  
  
1.  **색상** 창에서 **화면색** 선택기나 **반전색** 선택기를 선택합니다.  
  
2.  그리기 도구를 사용하여 이미지에 화면 색이나 반전 색을 적용합니다.  그리기 도구에 대한 자세한 내용은 [Using a Drawing Tool](../mfc/using-a-drawing-tool-image-editor-for-icons.md)을 참조하십시오.  
  
### 화면색이나 반전색을 변경하려면  
  
1.  **화면색** 선택기나 **반전색** 선택기 중 하나를 선택합니다.  
  
2.  **색상** 창의 **색** 색상표에서 색을 선택합니다.  
  
     그러면 다른 선택기에 자동으로 보색이 지정됩니다.  
  
    > [!TIP]
    >  화면색 또는 반전색 선택기를 두 번 클릭하면 [사용자 지정 색 선택 대화 상자](../windows/custom-color-selector-dialog-box-image-editor-for-icons.md)가 표시됩니다.  
  
 관리되는 프로젝트에 리소스를 추가하는 방법은 .NET Framework 개발자 가이드의 [응용 프로그램의 리소스](../Topic/Resources%20in%20Desktop%20Apps.md)를 참조하십시오. 관리되는 프로젝트에 리소스 파일 추가, 리소스 액세스, 정적 리소스 표시, 속성에 리소스 문자열 할당 등의 작업을 수동으로 수행하는 방법에 대한 자세한 내용은 [연습: Windows Forms 지역화](http://msdn.microsoft.com/ko-kr/9a96220d-a19b-4de0-9f48-01e5d82679e5) 및 [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)을 참조하십시오.  
  
 요구 사항  
  
 없음  
  
## 참고 항목  
 [Accelerator Keys](../mfc/accelerator-keys-image-editor-for-icons.md)   
 [Icons and Cursors: Image Resources for Display Devices](../mfc/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)