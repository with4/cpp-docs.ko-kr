---
title: "Editing Parts of an Image (Image Editor for Icons) | Microsoft Docs"
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
  - "Image editor [C++], editing images"
  - "Clipboard [C++], pasting"
  - "images [C++], editing"
  - "images [C++], deleting selected parts"
  - "images [C++], copying selected parts"
  - "images [C++], moving selected parts"
  - "images [C++], dragging and replicating selected parts"
  - "images [C++], pasting into"
  - "graphics [C++], editing"
ms.assetid: ff4f5fef-71a4-4fd8-825e-049399fed391
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Editing Parts of an Image (Image Editor for Icons)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

선택 영역이 이미지의 일부 또는 전체이든지 관계 없이 [선택 영역](../mfc/selecting-an-area-of-an-image-image-editor-for-icons.md)에 대하여 잘라내기, 복사, 지우기 및 이동과 같은 표준 편집 작업을 수행할 수 있습니다.  이미지 편집기는 Windows 클립보드를 사용 하 여 있기 때문에 이미지 편집기와 다른 Windows 용 응용 프로그램 간에 이미지를 전송할 수 있습니다.  
  
 또한 선택 영역이 이미지의 일부를 포함하든지 전체를 포함하든지 관계 없이 선택 영역의 크기를 조정할 수 있습니다.  
  
### 현재 선택 영역을 잘라내서 클립보드로 이동하려면  
  
1.  **편집** 메뉴에서 **잘라내기**를 클릭합니다.  
  
### 선택 영역을 복사하려면  
  
1.  크기 조정 핸들을 제외한 선택 영역 테두리나 그 안에 포인터를 놓습니다.  
  
2.  **Ctrl** 키를 누른 상태에서 새 위치로 선택 영역을 끕니다.  원래 선택 영역은 변경되지 않습니다.  
  
3.  현재 위치의 이미지에 선택 영역을 복사하려면 선택 커서의 외부를 클릭합니다.  
  
### 클립보드 내용을 이미지에 붙여 넣으려면  
  
1.  **편집** 메뉴에서 **붙여넣기**를 선택합니다.  
  
     그러면 선택 테두리에 포함된 클립보드 내용이 창의 왼쪽 위 모퉁이에 표시됩니다.  
  
2.  선택 영역 테두리 안에 포인터를 놓고 해당 이미지를 이미지의 원하는 위치로 끕니다.  
  
3.  새 위치에 이미지를 고정하려면 선택 영역 테두리 외부를 클릭합니다.  
  
### 현재 선택 영역을 클립보드로 이동하지 않고 삭제하려면  
  
1.  **편집** 메뉴에서 **삭제**를 선택합니다.  
  
     그러면 원래 선택 영역이 현재 배경색으로 채워집니다.  
  
    > [!NOTE]
    >  리소스 뷰 창을 마우스 오른쪽 단추로 클릭하면 잘라내기, 복사, 붙여넣기 및 삭제 명령을 사용할 수 있습니다.  
  
### 선택 영역을 이동하려면  
  
1.  크기 조정 핸들을 제외한 선택 영역 테두리나 그 안에 포인터를 놓습니다.  
  
2.  새 위치로 선택 영역을 끕니다.  
  
3.  새 위치의 이미지에 선택 영역을 고정하려면 선택 영역 테두리 외부를 클릭합니다.  
  
 선택 영역을 사용하여 그리기에 대한 자세한 내용은 [사용자 지정 브러시 만들기](../mfc/creating-a-custom-brush-image-editor-for-icons.md)를 참조하십시오.  
  
 관리되는 프로젝트에 리소스를 추가하는 방법은 .NET Framework 개발자 가이드의 [응용 프로그램의 리소스](../Topic/Resources%20in%20Desktop%20Apps.md)를 참조하십시오. 관리되는 프로젝트에 리소스 파일 추가, 리소스 액세스, 정적 리소스 표시, 속성에 리소스 문자열 할당 등의 작업을 수동으로 수행하는 방법에 대한 자세한 내용은 [연습: Windows Forms 지역화](http://msdn.microsoft.com/ko-kr/9a96220d-a19b-4de0-9f48-01e5d82679e5) 및 [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)을 참조하십시오.  
  
 요구 사항  
  
 없음  
  
## 참고 항목  
 [Accelerator Keys](../mfc/accelerator-keys-image-editor-for-icons.md)   
 [Editing Graphical Resources](../mfc/editing-graphical-resources-image-editor-for-icons.md)   
 [Image Editor for Icons](../mfc/image-editor-for-icons.md)