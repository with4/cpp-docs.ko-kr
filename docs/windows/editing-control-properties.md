---
title: "Editing Control Properties | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "controls [C++], undoing changes"
  - "controls [C++], editing properties"
  - "dialog box controls, editing properties"
ms.assetid: 9bdae21d-6dec-4344-a197-2ca4fc46d040
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Editing Control Properties
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

### 하나 이상의 컨트롤 속성을 편집하려면  
  
1.  대화 상자에서 수정할 컨트롤을 선택합니다.  
  
    > [!NOTE]
    >  여러 개의 컨트롤을 선택한 경우에는 선택한 모든 컨트롤에 공통인 속성만 편집할 수 있습니다.  
  
2.  [속성 창](../Topic/Properties%20Window.md)에서 컨트롤의 속성을 변경합니다.  
  
    > [!NOTE]
    >  단추, 라디오 단추 또는 확인란 컨트롤의 **Bitmap** 속성을 **True**와 같은 값으로 설정하면 컨트롤에 BS\_BITMAP 스타일이 구현됩니다.  자세한 내용은 [단추 스타일](../mfc/reference/button-styles.md)을 참조하십시오.  컨트롤에 비트맵을 연결하는 예제를 보려면 [CButton::SetBitmap](../Topic/CButton::SetBitmap.md)을 참조하십시오.  대화 상자 리소스 편집기에 있는 동안에는 비트맵이 컨트롤에 나타나지 않습니다.  
  
### 컨트롤 속성에 변경한 내용을 취소하려면  
  
1.  대화 상자 편집기에서 컨트롤에 포커스가 있는지 확인합니다.  
  
2.  **편집** 메뉴에서 **실행 취소**를 선택합니다. 컨트롤에 포커스가 없으면 **실행 취소** 명령을 사용할 수 없습니다.  
  
 관리되는 프로젝트에 리소스를 추가하는 방법은 .NET Framework 개발자 가이드의 [응용 프로그램의 리소스](../Topic/Resources%20in%20Desktop%20Apps.md)를 참조하십시오. 관리되는 프로젝트에 리소스 파일 추가, 리소스 액세스, 정적 리소스 표시, 속성에 리소스 문자열 할당 등의 작업을 수동으로 수행하는 방법에 대한 자세한 내용은 [연습: Windows Forms 지역화](http://msdn.microsoft.com/ko-kr/9a96220d-a19b-4de0-9f48-01e5d82679e5) 및 [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)을 참조하십시오.  
  
 요구 사항  
  
 Win32  
  
## 참고 항목  
 [Controls in Dialog Boxes](../mfc/controls-in-dialog-boxes.md)