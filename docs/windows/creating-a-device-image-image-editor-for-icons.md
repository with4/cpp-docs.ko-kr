---
title: "Creating a Device Image (Image Editor for Icons) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.icon"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cursors [C++], creating"
  - "icons [C++], creating"
  - "display devices"
  - "display devices, creating image"
  - "images [C++], creating for display devices"
  - "icons [C++], inserting"
ms.assetid: 5a536928-32df-4ace-beb1-1521ce3b871f
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Creating a Device Image (Image Editor for Icons)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

새 아이콘이나 커서 리소스를 만들 경우, 이미지 편집기에서는 특정 스타일\(아이콘의 경우 32 × 32, 16색, 커서의 경우 32 × 32, 단색\)의 이미지를 먼저 만듭니다.  그런 다음, 처음에 만들어진 아이콘이나 커서에 다른 크기와 스타일의 이미지를 추가하거나, 필요에 따라 다른 디스플레이 장치용으로 각 추가 이미지를 편집할 수 있습니다.  기존 이미지 형식이나 그래픽 프로그램에서 만들어진 비트맵에서 잘라내어 붙여넣기 작업을 수행하여 이미지를 편집할 수도 있습니다.  Windows에서 사용하는 아이콘 크기에 대한 자세한 내용은 Windows SDK 설명서에서 [아이콘](_win32_Icons_cpp)을 참조하십시오.  
  
 [이미지 편집기](../mfc/image-editor-for-icons.md)에서 아이콘이나 커서 리소스를 열면 기본적으로 현재 디스플레이 장치에 가장 적합한 이미지가 열립니다.  
  
### 새 아이콘이나 커서를 만들려면  
  
1.  [리소스 뷰](../windows/resource-view-window.md)에서 .rc 파일을 마우스 오른쪽 단추로 클릭하고 바로 가기 메뉴에서 **리소스 삽입**을 선택합니다.  .rc 파일에 커서 같은 기존 이미지 리소스가 있으면 **Cursor** 폴더를 마우스 오른쪽 단추로 클릭하고 바로 가기 메뉴에서 **Cursor 삽입**을 선택합니다.  
  
    > [!NOTE]
    >  프로젝트에 .rc 파일이 없으면 [새 리소스 스크립트 파일 만들기](../windows/how-to-create-a-resource-script-file.md)를 참조하십시오.  
  
2.  [리소스 삽입 대화 상자](../windows/add-resource-dialog-box.md)에서 **아이콘**이나 **커서**를 선택하고 **새로 만들기**를 클릭합니다.  아이콘을 선택하면 32 × 32, 16 색 아이콘으로 이루어진 아이콘 리소스가 만들어집니다.  커서를 선택하면 32 × 32, 단색\(2색\) 이미지가 만들어집니다.  
  
     **리소스 삽입** 대화 상자의 이미지 리소스 종류 옆에 더하기 기호\(**\+**\)가 표시되면 도구 모음 템플릿을 사용할 수 있습니다.  더하기 기호\(\+\)를 클릭하여 템플릿 목록을 확장하고 템플릿을 선택한 다음 **새로 만들기**를 클릭합니다.  
  
 관리되는 프로젝트에 리소스를 추가하는 방법은 .NET Framework 개발자 가이드의 [응용 프로그램의 리소스](../Topic/Resources%20in%20Desktop%20Apps.md)를 참조하십시오. 관리되는 프로젝트에 리소스 파일 추가, 리소스 액세스, 정적 리소스 표시, 속성에 리소스 문자열 할당 등의 작업을 수동으로 수행하는 방법에 대한 자세한 내용은 [연습: Windows Forms 지역화](http://msdn.microsoft.com/ko-kr/9a96220d-a19b-4de0-9f48-01e5d82679e5) 및 [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)을 참조하십시오.  
  
 **요구 사항**  
  
 없음  
  
## 참고 항목  
 [Icons and Cursors: Image Resources for Display Devices](../mfc/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)   
 [Accelerator Keys](../mfc/accelerator-keys-image-editor-for-icons.md)   
 [Icons and Cursors: Image Resources for Display Devices](../mfc/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)