---
title: "Drawing Lines or Closed Figures (Image Editor for Icons) | Microsoft Docs"
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
  - "closed figures, drawing"
  - "lines [C++], painting"
  - "lines [C++], drawing"
  - "Image editor [C++], drawing lines"
  - "shapes, drawing"
ms.assetid: 7edd86db-77b1-451f-8001-bbfed9c6304f
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Drawing Lines or Closed Figures (Image Editor for Icons)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

선과 닫힌 그림을 그리는 이미지 편집기 도구는 동일한 방식으로 작동합니다. 즉, 한 지점에 커서를 놓고 다른 지점으로 끌면 됩니다.  선의 경우는 이러한 지점이 끝점입니다.  닫힌 그림에서 이러한 지점은 그림의 사각형 경계의 반대편 모퉁이가 됩니다.  
  
 선은 현재 브러시를 선택할  때 결정한 두께로 그려지고, 틀이 있는 그림은 현재 두께를 선택할 때 결정한 두께로 그려집니다.  틀이 있고 채워진 그림과 선은 모두 마우스 왼쪽 단추를 누르면 현재의 전경색으로 그려지고 마우스 오른쪽 단추를 누르면 현재의 배경색으로 그려집니다.  
  
### 선을 그리려면  
  
1.  [이미지 편집기 도구 모음](../mfc/toolbar-image-editor-for-icons.md)에서 또는 **이미지** 메뉴의 **도구** 명령을 사용하여 **선** 도구를 클릭합니다.  
  
2.  필요하면 다음과 같이 색과 브러시를 선택합니다.  
  
    -   [색상 창](../windows/colors-window-image-editor-for-icons.md)에서 전경색을 선택하려면 마우스 왼쪽 단추를 클릭하고 배경색을 선택하려면 마우스 오른쪽 단추를 클릭합니다.  
  
    -   [이미지 편집기 도구 모음](../mfc/toolbar-image-editor-for-icons.md)에서 사용할 브러시를 나타내는 모양을 클릭합니다.  
  
3.  선의 시작 지점에 포인터를 놓습니다.  
  
4.  선의 끝점까지 끕니다.  
  
### 닫힌 그림을 그리려면  
  
1.  **이미지 편집기** 도구 모음에서 또는 **이미지** 메뉴의 **도구** 명령을 사용하여 **닫힌 그림 그리기** 도구를 클릭합니다.  
  
     **닫힌 그림 그리기** 도구는 각 단추에 표시된 대로 그림을 만듭니다.  
  
2.  필요하면 색과 선 두께를 선택합니다.  
  
3.  그림을 그릴 사각형 영역의 한 쪽 모퉁이로 포인터를 이동합니다.  
  
4.  포인터를 대각선 방향 반대쪽 모퉁이로 끕니다.  
  
 관리되는 프로젝트에 리소스를 추가하는 방법은 .NET Framework 개발자 가이드의 [응용 프로그램의 리소스](../Topic/Resources%20in%20Desktop%20Apps.md)를 참조하십시오. 관리되는 프로젝트에 리소스 파일 추가, 리소스 액세스, 정적 리소스 표시, 속성에 리소스 문자열 할당 등의 작업을 수동으로 수행하는 방법에 대한 자세한 내용은 [연습: Windows Forms 지역화](http://msdn.microsoft.com/ko-kr/9a96220d-a19b-4de0-9f48-01e5d82679e5) 및 [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)을 참조하십시오.  
  
 요구 사항  
  
 없음  
  
## 참고 항목  
 [Accelerator Keys](../mfc/accelerator-keys-image-editor-for-icons.md)   
 [Editing Graphical Resources](../mfc/editing-graphical-resources-image-editor-for-icons.md)   
 [Image Editor for Icons](../mfc/image-editor-for-icons.md)   
 [Working with Color](../mfc/working-with-color-image-editor-for-icons.md)