---
title: "Window Panes (Image Editor for Icons) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.bitmap"
  - "vc.editors.icon"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "graphics editor [C++]"
  - "Image editor [C++], panes"
ms.assetid: d66ea5b3-e2e2-4fc4-aa99-f50022cc690e
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Window Panes (Image Editor for Icons)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

일반적으로 이미지 편집기 창은 분할 막대로 구분된 두 창에 이미지를 표시합니다.  뷰 하나는 실제 크기이고 다른 하나는 확대된 것으로, 기본 확대 비율은 6입니다.  이러한 두 창의 뷰는 자동으로 업데이트됩니다. 즉 하나의 창에서 변경한 내용이 즉시 다른 창에 표시됩니다.  개별 픽셀을 구분할 수 있는 확대된 이미지 뷰에서 작업하면서 동시에 이미지의 실제 크기 뷰에서 작업 결과를 확인할 수 있는 두 창이 있어 편리하게 작업할 수 있습니다.  
  
 왼쪽 창에서는 이미지 창의 최대 1\/2까지 필요한 만큼의 공간을 사용하여 이미지를 기본값 1:1 비율로 표시합니다.  오른쪽 창에서는 기본값 6:1 비율로 확대된 이미지를 표시합니다.  각 창에서 [이미지 편집기 도구 모음](../mfc/toolbar-image-editor-for-icons.md)의 **확대** 도구를 사용하거나 액셀러레이터 키를 사용하여 [확대 비율을 변경](../mfc/changing-the-magnification-factor-image-editor-for-icons.md)할 수 있습니다.  
  
 이미지 편집기 창 중에서 작은 창을 확대할 수 있고 두 창을 사용하여 큰 이미지의 서로 다른 영역을 표시할 수 있습니다.  창 내부를 클릭하여 이미지를 선택합니다.  
  
 포인터를 분할 막대 위에 놓고 분할 막대를 오른쪽이나 왼쪽으로 이동하여 창의 크기를 상대적으로 변경할 수 있습니다.  하나의 창에서만 작업하려면 분할 막대를 다른 쪽 끝까지 이동하면 됩니다.  
  
 이미지 편집기 창이 4배 이상으로 확대되면 [픽셀 모눈을 표시](../mfc/displaying-or-hiding-the-pixel-grid-image-editor-for-icons.md)하여 이미지의 개별 픽셀을 구분할 수 있습니다.  
  
 관리되는 프로젝트에 리소스를 추가하는 방법은 .NET Framework 개발자 가이드의 [응용 프로그램의 리소스](../Topic/Resources%20in%20Desktop%20Apps.md)를 참조하십시오. 관리되는 프로젝트에 리소스 파일 추가, 리소스 액세스, 정적 리소스 표시, 속성에 리소스 문자열 할당 등의 작업을 수동으로 수행하는 방법에 대한 자세한 내용은 [연습: Windows Forms 지역화](http://msdn.microsoft.com/ko-kr/9a96220d-a19b-4de0-9f48-01e5d82679e5) 및 [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)을 참조하십시오.  
  
## 요구 사항  
 없음  
  
## 참고 항목  
 [Accelerator Keys](../mfc/accelerator-keys-image-editor-for-icons.md)   
 [Image Editor for Icons](../mfc/image-editor-for-icons.md)