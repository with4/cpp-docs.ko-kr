---
title: "Icons and Cursors: Image Resources for Display Devices (Image Editor for Icons) | Microsoft Docs"
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
  - "image resources, display devices"
  - "icons [C++], creating"
  - "cursors [C++], types"
  - "icons [C++]"
  - "Image editor [C++], icons and cursors"
  - "cursors [C++]"
  - "display devices, creating icons for"
  - "cursors [C++], hot spots"
  - "icons [C++], types"
ms.assetid: 8f0809a8-0cf0-4da9-b23d-51f28bf15f5b
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# Icons and Cursors: Image Resources for Display Devices (Image Editor for Icons)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

아이콘 및 커서는 다양한 유형의 디스플레이 장치에 맞는 다양한 크기 및 색 구성표의 여러 이미지를 포함할 수 있는 그래픽 리소스입니다. 또한 커서에는 Windows에서 해당 위치를 추적하는 데 사용하는 위치인 "핫스팟"이 있습니다. 비트맵 및 기타 이미지와 마찬가지로 아이콘과 커서는 모두 이미지 편집기를 사용하여 생성하고 편집할 수 있습니다.  
  
 새 아이콘 또는 커서를 만들 때 이미지 편집기는 먼저 표준 형식의 이미지를 만듭니다. 이미지는 처음에 투명한 화면 색상으로 채워집니다. 이미지가 커서인 경우 핫스팟은 처음에 왼쪽 위 모서리\(좌표 0, 0\)에 있습니다.  
  
 기본적으로 이미지 편집기는 다음 표에 표시된 장치의 추가 이미지 만들기를 지원합니다.[사용자 지정 이미지 대화 상자](../mfc/custom-image-dialog-box-image-editor-for-icons.md)에 너비, 높이 및 색상 수 매개 변수를 입력하여 기타 장치의 이미지를 만들 수 있습니다.  
  
> [!NOTE]
>  이미지 편집기를 사용하여 32비트 이미지를 볼 수는 있지만 편집할 수는 없습니다.  
  
|색|너비\(픽셀\)|높이\(픽셀\)|  
|-------|--------------|--------------|  
|단색|16|16|  
|단색|32|32|  
|단색|48|48|  
|단색|64|64|  
|단색|96|96|  
|16|16|16|  
|16|32|32|  
|16|64|64|  
|16|48|48|  
|16|96|96|  
|256|16|16|  
|256|32|32|  
|256|48|48|  
|256|64|64|  
|256|96|96|  
  
-   [새 장치 이미지 만들기\(아이콘 또는 커서\)](../mfc/creating-a-device-image-image-editor-for-icons.md)  
  
-   [다른 디스플레이 장치용 이미지 추가](../mfc/adding-an-image-for-a-different-display-device-image-editor-for-icons.md)  
  
-   [장치 이미지 복사](../mfc/copying-a-device-image-image-editor-for-icons.md)  
  
-   [장치 이미지 삭제](../mfc/deleting-a-device-image-image-editor-for-icons.md)  
  
-   [장치 이미지에서 투명한 영역이나 반전 영역 만들기](../mfc/creating-transparent-or-inverse-regions-in-device-images.md)  
  
-   [256색 아이콘이나 커서 만들기](../mfc/creating-a-256-color-icon-or-cursor-image-editor-for-icons.md)  
  
-   [커서의 핫스팟 설정](../mfc/setting-a-cursor-s-hot-spot-image-editor-for-icons.md)  
  
 관리되는 프로젝트에 리소스를 추가하는 방법은 *.NET Framework 개발자 가이드*에서 [응용 프로그램의 리소스](../Topic/Resources%20in%20Desktop%20Apps.md)를 참조하세요. 관리되는 프로젝트에 리소스 파일 추가, 리소스 액세스, 정적 리소스 표시, 속성에 리소스 문자열 할당 등의 작업을 수동으로 수행하는 방법에 대한 자세한 내용은 [연습: Windows Forms 지역화](http://msdn.microsoft.com/ko-kr/9a96220d-a19b-4de0-9f48-01e5d82679e5) 및 [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)을 참조하세요.  
  
## 요구 사항  
 없음  
  
## 참고 항목  
 [Image Editor for Icons](../mfc/image-editor-for-icons.md)   
 [아이콘](http://msdn.microsoft.com/library/windows/desktop/ms646973)   
 [커서](http://msdn.microsoft.com/library/windows/desktop/ms646970)