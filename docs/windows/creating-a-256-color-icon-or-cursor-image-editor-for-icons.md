---
title: "Creating a 256-Color Icon or Cursor (Image Editor for Icons) | Microsoft Docs"
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
  - "256-color palette"
  - "cursors, color"
  - "colors, icons"
  - "colors, cursors"
  - "icons, color"
ms.assetid: 2738089b-4fd3-4c45-96ae-6a15e4c6b780
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Creating a 256-Color Icon or Cursor (Image Editor for Icons)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이미지 편집기를 사용하면 원하는 색을 선택할 수 있는 256 색상표를 가진 크기가 큰\(64 × 64\) 아이콘과 커서를 만들 수 있습니다.  리소스를 만들고 나면 장치 이미지 스타일이 선택됩니다.  
  
### 256색 아이콘이나 커서를 만들려면  
  
1.  [리소스 뷰](../windows/resource-view-window.md)에서 .rc 파일을 마우스 오른쪽 단추로 클릭하고 바로 가기 메뉴에서 **리소스 삽입**을 선택합니다.  .rc 파일에 커서 같은 기존 이미지 리소스가 있으면 **Cursor** 폴더를 마우스 오른쪽 단추로 클릭하고 바로 가기 메뉴에서 **Cursor  삽입**을 선택합니다.  
  
     **참고** 프로젝트에 .rc 파일이 없으면 [새 리소스 스크립트 파일 만들기](../windows/how-to-create-a-resource-script-file.md)를 참조하십시오.  
  
2.  [리소스 삽입 대화 상자](../windows/add-resource-dialog-box.md)에서 **아이콘**이나 **커서**를 선택하고 **새로 만들기**를 클릭합니다.  
  
3.  **이미지** 메뉴에서 **새 장치 이미지**를 클릭합니다.  
  
4.  원하는 256색 이미지 스타일을 선택합니다.  
  
 관리되는 프로젝트에 리소스를 추가하는 방법은 .NET Framework 개발자 가이드의 [응용 프로그램의 리소스](../Topic/Resources%20in%20Desktop%20Apps.md)를 참조하십시오. 관리되는 프로젝트에 리소스 파일 추가, 리소스 액세스, 정적 리소스 표시, 속성에 리소스 문자열 할당 등의 작업을 수동으로 수행하는 방법에 대한 자세한 내용은 [연습: Windows Forms 지역화](http://msdn.microsoft.com/ko-kr/9a96220d-a19b-4de0-9f48-01e5d82679e5) 및 [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)을 참조하십시오.  
  
 **요구 사항**  
  
 없음  
  
## 참고 항목  
 [Using the 256\-Color Palette](../mfc/using-the-256-color-palette-image-editor-for-icons.md)   
 [Accelerator Keys](../mfc/accelerator-keys-image-editor-for-icons.md)   
 [Icons and Cursors: Image Resources for Display Devices](../mfc/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)