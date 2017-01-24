---
title: "Creating a Custom Brush (Image Editor for Icons) | Microsoft Docs"
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
  - "colors [C++], brush"
  - "brushes, colors"
  - "brushes, creating custom"
  - "images [C++], creating custom brushes"
  - "graphics [C++], custom brushes"
  - "custom brushes"
ms.assetid: 750881aa-6f47-4de9-8ca6-a7a12afc6383
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Creating a Custom Brush (Image Editor for Icons)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

사용자 지정 브러시는 이미지 편집기에 포함되어 있는 브러시처럼 선택해서 사용할 수 있는 이미지의 사각형 부분입니다.  선택 영역에 대하여 수행할 수 있는 모든 작업을 사용자 지정 브러시로도 수행할 수 있습니다.  
  
### 이미지 일부에서 사용자 지정 브러시를 만들려면  
  
1.  브러시로 사용할 [이미지 영역을 선택](../mfc/selecting-an-area-of-an-image-image-editor-for-icons.md)합니다.  
  
2.  **Shift** 키를 누른 채로 선택 영역 안쪽을 클릭하여 이미지 쪽으로 끕니다.  
  
     \-또는\-  
  
3.  **이미지** 메뉴에서 **선택 항목을 브러시로 사용**을 선택합니다.  
  
     그러면 선택 영역은 이미지의 선택 영역에 색을 분사하는 사용자 지정 브러시가 됩니다.  그리고 끌기 경로에 선택 영역의 복사본이 생깁니다.  느리게 끌수록 많은 복사본이 만들어집니다.  
  
     **참고** 이미지 부분을 먼저 선택하지 않고 **선택 항목을 브러시로 사용**을 클릭하면 전체 이미지가 브러시로 사용됩니다.  또한 사용자 지정 브러시를 사용할 경우 [투명 또는 불투명 배경](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md) 중 어느 배경을 선택하는지에 따라 결과가 달라집니다.  
  
 현재 배경색과 일치하는 사용자 지정 브러시의 픽셀은 일반적으로 투명이므로 기존 이미지를 칠하지는 않습니다.  배경색 픽셀이 기존 이미지를 칠하도록 이 동작을 변경할 수 있습니다.  
  
 스탬프나 스텐실같은 사용자 지정 브러시를 사용하여 다양한 특수 효과를 만들 수 있습니다.  
  
#### 배경색으로 사용자 지정 브러시 모양을 그리려면  
  
1.  [투명 또는 불투명 배경을 선택](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md)합니다.  
  
2.  그리려는 색으로 [배경색을 설정](../windows/selecting-foreground-or-background-colors-image-editor-for-icons.md)합니다.  
  
3.  그리려는 위치에 사용자 지정 브러시를 놓습니다.  
  
4.  마우스 오른쪽 단추를 누릅니다.  사용자 지정 브러시의 불투명 영역이 배경색으로 그려집니다.  
  
#### 사용자 지정 브러시 크기를 두 배로 늘리거나 반으로 줄이려면  
  
1.  브러시 크기를 두 배로 하려면 **더하기 부호**\(**\+**\) 키를 누르고 반으로 줄이려면 **빼기 부호**\(**–**\) 키를 누릅니다.  
  
#### 사용자 지정 브러시를 취소하려면  
  
1.  **Esc** 키를 누르거나 다른 그리기 도구를 선택합니다.  
  
 관리되는 프로젝트에 리소스를 추가하는 방법은 .NET Framework 개발자 가이드의 [응용 프로그램의 리소스](../Topic/Resources%20in%20Desktop%20Apps.md)를 참조하십시오. 관리되는 프로젝트에 리소스 파일 추가, 리소스 액세스, 정적 리소스 표시, 속성에 리소스 문자열 할당 등의 작업을 수동으로 수행하는 방법에 대한 자세한 내용은 [연습: Windows Forms 지역화](http://msdn.microsoft.com/ko-kr/9a96220d-a19b-4de0-9f48-01e5d82679e5) 및 [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)을 참조하십시오.  
  
### 요구 사항  
 없음  
  
## 참고 항목  
 [Accelerator Keys](../mfc/accelerator-keys-image-editor-for-icons.md)   
 [Editing Graphical Resources](../mfc/editing-graphical-resources-image-editor-for-icons.md)   
 [Image Editor for Icons](../mfc/image-editor-for-icons.md)