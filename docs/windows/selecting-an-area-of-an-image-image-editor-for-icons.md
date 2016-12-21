---
title: "Selecting an Area of an Image (Image Editor for Icons) | Microsoft Docs"
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
  - "vc.editors.image.editing"
dev_langs: 
  - "C++"
  - "C++"
helpviewer_keywords: 
  - "Image editor [C++], image selection"
  - "Image editor [C++], selecting images"
  - "images [C++], selecting"
  - "cursors [C++], selecting areas of"
ms.assetid: 8b6ce4ad-eba1-4ece-86ba-cea92c3edff2
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Selecting an Area of an Image (Image Editor for Icons)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

선택 도구를 사용하여 잘라내기, 복사, 지우기, 크기 조정, 반전 및 이동 작업을 할 이미지 영역을 지정할 수 있습니다.  **사각형 선택** 도구를 사용하면 이미지의 사각 영역을 지정하고 선택할 수 있습니다.  **부정형** 도구를 사용하면 잘라내기, 복사 또는 다른 작업을 위해 선택할 영역의 윤곽선을 자유롭게 그릴 수 있습니다.  
  
> [!NOTE]
>  [이미지 편집기 도구 모음](../mfc/toolbar-image-editor-for-icons.md)에 표시된 **사각형 선택** 및 **부정형 선택** 도구를 보거나 **이미지 편집기** 도구 모음에 있는 각 단추에 대한 도구 설명을 보십시오.  
  
 선택 영역에서 사용자 지정 브러시를 만들 수도 있습니다.  자세한 내용은 [사용자 지정 브러시 만들기](../mfc/creating-a-custom-brush-image-editor-for-icons.md)를 참조하십시오.  
  
### 이미지 영역을 선택하려면  
  
1.  **이미지 편집기** 도구 모음에서 또는 **이미지** 메뉴의 **도구** 명령을 사용하여 원하는 선택 도구를 클릭합니다.  
  
2.  선택할 이미지 영역의 한 쪽 모퉁이로 커서를 이동합니다.  이미지 위에 커서를 올려 놓으면 십자 모양이 표시됩니다.  
  
3.  선택할 영역의 반대 모퉁이로 커서를 끕니다.  선택할 픽셀이 사각형으로 표시됩니다.  사각형 테두리와 안에 포함된 모든 픽셀이 선택 영역에 포함됩니다.  
  
4.  마우스 단추를 놓습니다.  선택 테두리에 선택된 영역이 포함됩니다.  
  
### 전체 이미지를 선택하려면  
  
1.  현재 선택 영역의 외부에 있는 이미지를 클릭합니다.  그러면 선택 테두리에 따라 포커스가 변경되고 전체 이미지가 다시 포함됩니다.  
  
 관리되는 프로젝트에 리소스를 추가하는 방법은 .NET Framework 개발자 가이드의 [응용 프로그램의 리소스](../Topic/Resources%20in%20Desktop%20Apps.md)를 참조하십시오. 관리되는 프로젝트에 리소스 파일 추가, 리소스 액세스, 정적 리소스 표시, 속성에 리소스 문자열 할당 등의 작업을 수동으로 수행하는 방법에 대한 자세한 내용은 [연습: Windows Forms 지역화](http://msdn.microsoft.com/ko-kr/9a96220d-a19b-4de0-9f48-01e5d82679e5) 및 [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)을 참조하십시오.  
  
 요구 사항  
  
 없음  
  
## 참고 항목  
 [Accelerator Keys](../mfc/accelerator-keys-image-editor-for-icons.md)   
 [Editing Graphical Resources](../mfc/editing-graphical-resources-image-editor-for-icons.md)   
 [Image Editor for Icons](../mfc/image-editor-for-icons.md)