---
title: "Working with Color (Image Editor for Icons) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.image.color"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "images [C++], background colors"
  - "Image editor [C++], Colors Palette"
  - "colors [C++], image"
  - "Colors Palette, Image editor"
  - "palettes, Image editor colors"
  - "foreground colors, Image editor"
  - "colors [C++]"
ms.assetid: d34ff96f-241d-494f-abdd-13811ada8cd3
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Working with Color (Image Editor for Icons)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이미지 편집기에는 색을 처리하고 사용자 지정할 수 있는 많은 기능이 포함되어 있습니다.  전경색이나 배경색을 설정하고, 경계 영역을 색으로 채우고, 이미지에서 색을 선택하여 현재 전경색이나 배경색으로 사용할 수 있습니다.  [이미지 편집기 도구 모음](../mfc/toolbar-image-editor-for-icons.md)에 있는 도구와 [색상 창](../windows/colors-window-image-editor-for-icons.md)의 색상표를 함께 사용하여 이미지를 만들 수 있습니다.  
  
 단색과 16색 이미지에 사용되는 모든 색이 색상 창에 있는 색상표에 표시됩니다.  16 표준 색 이외에 사용자 지정 색도 만들 수 있습니다.  색상표에 있는 색을 변경하는 즉시 이미지에 있는 해당 색도 변합니다.  
  
 256색 아이콘과 커서 이미지로 작업을 할 때는 [속성 창](../Topic/Properties%20Window.md)에 있는 Colors 속성이 사용됩니다.  자세한 내용은 [256색 아이콘이나 커서 만들기](../mfc/creating-a-256-color-icon-or-cursor-image-editor-for-icons.md)를 참조하십시오.  
  
> [!NOTE]
>  이미지 편집기를 사용하여 32비트 이미지를 볼 수는 있지만 편집할 수는 없습니다.  
  
 트루 컬러 이미지도 만들 수 있습니다.  그러나 트루 컬러 샘플은 색상 창에 있는 전체 색상표에 표시되지 않고 전경색 또는 배경색 표시기 영역에만 표시됩니다.  트루 컬러는 [사용자 지정 색 선택 대화 상자](../windows/custom-color-selector-dialog-box-image-editor-for-icons.md)를 사용하여 만들어집니다.  자세한 내용은 [색 사용자 지정 또는 변경](../windows/customizing-or-changing-colors-image-editor-for-icons.md)을 참조하십시오.  
  
 사용자 지정 색상표를 디스크에 저장해 두고 필요할 때마다 다시 로드할 수 있습니다.  가장 최근에 사용한 색상표는 레지스트리에 저장되며 다음에 Visual Studio를 시작하면 자동으로 로드됩니다.  
  
-   [전경색 또는 배경색 선택](../windows/selecting-foreground-or-background-colors-image-editor-for-icons.md)  
  
-   [이미지 경계 영역을 색으로 채우기](../windows/filling-a-bounded-area-of-an-image-with-a-color-image-editor-for-icons.md)  
  
-   [이미지에서 색을 선택하여 다른 곳에 사용](../windows/picking-up-a-color-from-an-image-to-use-elsewhere-image-editor-for-icons.md)  
  
-   [투명 또는 불투명 배경 선택](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md)  
  
-   [선택 영역에서 색 반전](../windows/inverting-the-colors-in-a-selection-image-editor-for-icons.md)  
  
-   [색 사용자 지정 또는 변경](../windows/customizing-or-changing-colors-image-editor-for-icons.md)  
  
-   [다른 색상표 저장 및 로드](../windows/saving-and-loading-different-color-palettes-image-editor-for-icons.md)  
  
-   [색상 창](../windows/colors-window-image-editor-for-icons.md)  
  
 관리되는 프로젝트에 리소스를 추가하는 방법은 .NET Framework 개발자 가이드의 [응용 프로그램의 리소스](../Topic/Resources%20in%20Desktop%20Apps.md)를 참조하십시오. 관리되는 프로젝트에 리소스 파일 추가, 리소스 액세스, 정적 리소스 표시, 속성에 리소스 문자열 할당 등의 작업을 수동으로 수행하는 방법에 대한 자세한 내용은 [연습: Windows Forms 지역화](http://msdn.microsoft.com/ko-kr/9a96220d-a19b-4de0-9f48-01e5d82679e5) 및 [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)을 참조하십시오.  
  
## 요구 사항  
 없음  
  
## 참고 항목  
 [Accelerator Keys](../mfc/accelerator-keys-image-editor-for-icons.md)   
 [리소스](_win32_Resources)