---
title: "Image Editor for Icons | Microsoft Docs"
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
  - "vc.editors.cursor.F1"
  - "vc.editors.icon.F1"
  - "vc.editors.cursor"
  - "vc.editors.bitmap.F1"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "editors, images"
  - "resource editors, graphics"
  - "Image editor [C++]"
  - "resource editors, Image editor"
ms.assetid: 586d2b8b-0348-4883-a85d-1ff0ddbf14dd
caps.latest.revision: 17
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Image Editor for Icons
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이미지 편집기에는 도구 모음 비트맵 만들기에 도움이 되는 기능뿐 아니라 이미지 만들기와 편집에 사용하는 다양한 도구도 들어 있습니다.**이미지 편집기** 도구 모음에서 **이미지** 메뉴와 도구의 명령을 사용하여 비트맵, 아이콘 및 커서뿐 아니라 GIF나 JPEG 형식의 이미지도 편집할 수 있습니다.  
  
 이미지 편집기를 사용하면 다음과 같은 작업을 할 수 있습니다.  
  
-   [그래픽 리소스 편집](../mfc/editing-graphical-resources-image-editor-for-icons.md)  
  
-   [색 작업](../mfc/working-with-color-image-editor-for-icons.md)  
  
-   [아이콘과 커서를 사용한 작업: 디스플레이 장치용 이미지 리소스](../mfc/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)  
  
-   [이미지 편집기의 액셀러레이터 키 명령 사용](../mfc/accelerator-keys-image-editor-for-icons.md)  
  
 이미지 편집기 창에는 분할줄로 분리된 두 창에 이미지 뷰 두 개가 표시됩니다. 분할줄을 한 쪽에서 다른 쪽으로 끌면 창의 상대적 크기를 변경할 수 있습니다. 활성 창에는 선택 테두리가 표시됩니다.  
  
 사용자가 원하는 대로 이미지 편집기 창을 조정할 수 있습니다.[확대 비율을 변경](../mfc/changing-the-magnification-factor-image-editor-for-icons.md)하거나 [픽셀 모눈을 표시 또는 숨길](../mfc/displaying-or-hiding-the-pixel-grid-image-editor-for-icons.md) 수 있습니다.  
  
> [!NOTE]
>  이미지 편집기를 사용하여 32비트 이미지를 볼 수는 있지만 편집할 수는 없습니다.  
  
## Visual Studio 이미지 라이브러리  
 응용 프로그램에 사용할 수 있는 여러 애니메이션, 비트맵 및 아이콘을 포함하는 Visual Studio 이미지 라이브러리를 무료로 다운로드할 수 있습니다. 라이브러리를 다운로드하는 방법에 대한 자세한 내용은 [Visual Studio 이미지 라이브러리](../Topic/The%20Visual%20Studio%20Image%20Library.md)를 참조하십시오.  
  
## 관리되는 리소스  
 관리되는 프로젝트에서 리소스 파일에 대해 작업할 때는 이미지 편집기와 [바이너리 편집기](../mfc/binary-editor.md)를 사용할 수 있습니다. 편집할 관리되는 리소스는 연결된 리소스여야 합니다. Visual Studio 리소스 편집기에서는 포함된 리소스를 편집할 수 없습니다.  
  
 관리되는 프로젝트에 리소스를 추가하는 방법은 *.NET Framework 개발자 가이드*에서 [응용 프로그램의 리소스](../Topic/Resources%20in%20Desktop%20Apps.md)를 참조하세요. 관리되는 프로젝트에 리소스 파일 추가, 리소스 액세스, 정적 리소스 표시, 속성에 리소스 문자열 할당 등의 작업을 수동으로 수행하는 방법에 대한 자세한 내용은 [연습: Windows Forms 지역화](http://msdn.microsoft.com/ko-kr/9a96220d-a19b-4de0-9f48-01e5d82679e5) 및 [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)을 참조하세요.  
  
### 요구 사항  
 없음  
  
## 참고 항목  
 [Resource Editors](../mfc/resource-editors.md)   
 [아이콘](http://msdn.microsoft.com/library/windows/desktop/ms646973.aspx)