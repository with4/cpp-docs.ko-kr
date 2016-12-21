---
title: "Saving Bitmaps as GIFs or JPEGs (Image Editor for Icons) | Microsoft Docs"
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
  - ".gif files, saving bitmaps as"
  - "jpg files, saving bitmaps as"
  - "jpeg files, saving bitmaps as"
  - ".jpg files, saving bitmaps as"
  - "Image editor [C++], converting image formats"
  - "gif files, saving bitmaps as"
  - "bitmaps [C++], converting formats"
  - ".jpeg files, saving bitmaps as"
  - "graphics [C++], converting formats"
  - "images [C++], converting formats"
ms.assetid: 115df69f-10fb-4e6f-906b-853c1e4a54af
caps.latest.revision: 12
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Saving Bitmaps as GIFs or JPEGs (Image Editor for Icons)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

비트맵을 만들 때 이미지는 비트맵 형식\(.bmp\)으로 만들어집니다.  그러나 이 이미지를 GIF나 JPEG 또는 다른 그래픽 형식으로 저장할 수 있습니다.  
  
> [!NOTE]
>  아이콘과 커서에는 이 절차가 적용되지 않습니다.  
  
### 비트맵을 .gif 또는 .jpeg로 만들고 저장하려면  
  
1.  **파일** 메뉴에서 **열기**를 선택한 다음 **파일**을 클릭합니다.  
  
2.  **새 파일 대화 상자**에서 **Visual C\+\+** 폴더를 클릭하고 **템플릿** 상자에서 **비트맵 파일\(.bmp\)**을 선택한 다음 **열기**를 클릭합니다.  
  
     그러면 **이미지** 편집기에 비트맵이 열립니다.  
  
3.  원하는 대로 새 비트맵을 변경합니다.  
  
4.  **이미지** 편집기에 비트맵을 열고 **파일** 메뉴에서 **다른 이름으로 *filename*.bmp 저장**을 클릭합니다.  
  
5.  **파일 이름** 상자에 표시할 파일 형식에 맞게 파일과 확장명에 지정할 이름을 **다른 이름으로 파일 저장** 대화 상자에 입력합니다.  예를 들어, myfile.gif와 같이 입력합니다.  
  
     **참고**  다른 파일 형식으로 저장하려면 프로젝트 외부에서 비트맵을 만들거나 열어야 합니다.  프로젝트 내에서 비트맵을 만들거나 열면 **다른 이름으로 저장** 명령을 사용할 수 없습니다.  자세한 내용은 [프로젝트 외부에서 리소스 스크립트 파일 열기\(독립 실행형\)](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)를 참조하십시오.  
  
6.  **저장**을 클릭합니다.  
  
 관리되는 프로젝트에 리소스를 추가하는 방법은 .NET Framework 개발자 가이드의 [응용 프로그램의 리소스](../Topic/Resources%20in%20Desktop%20Apps.md)를 참조하십시오. 관리되는 프로젝트에 리소스 파일 추가, 리소스 액세스, 정적 리소스 표시, 속성에 리소스 문자열 할당 등의 작업을 수동으로 수행하는 방법에 대한 자세한 내용은 [연습: Windows Forms 지역화](http://msdn.microsoft.com/ko-kr/9a96220d-a19b-4de0-9f48-01e5d82679e5) 및 [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)을 참조하십시오.  
  
## 참고 항목  
 [Editing Graphical Resources](../mfc/editing-graphical-resources-image-editor-for-icons.md)   
 [Image Editor for Icons](../mfc/image-editor-for-icons.md)