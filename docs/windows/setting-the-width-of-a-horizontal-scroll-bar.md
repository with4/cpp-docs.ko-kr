---
title: "Setting the Width of a Horizontal Scroll Bar | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "list controls, scroll bar width"
  - "CListBox::SetHorizontalExtent"
  - "controls [C++], scroll bar"
  - "scroll bars, displaying in controls"
  - "horizontal scroll bar width"
  - "CListBox class, scroll bar width"
  - "scroll bars, width"
ms.assetid: 51dad141-aa0b-46a3-a82c-46b80d603d94
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Setting the Width of a Horizontal Scroll Bar
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC 클래스를 사용하여 가로 스크롤 막대가 있는 목록 상자를 대화 상자에 추가하면 응용 프로그램에 스크롤 막대가 자동으로 표시되지 않습니다.  
  
### 스크롤 막대를 표시하려면  
  
1.  코드에서 [CListBox::SetHorizontalExtent](../Topic/CListBox::SetHorizontalExtent.md)를 호출하여 가장 넓은 요소에 최대 너비를 설정합니다.  
  
     이렇게 값을 설정하지 않으면 목록 상자의 항목이 상자보다 넓을 경우에도 스크롤 막대가 표시되지 않습니다.  
  
 관리되는 프로젝트에 리소스를 추가하는 방법은 .NET Framework 개발자 가이드의 [응용 프로그램의 리소스](../Topic/Resources%20in%20Desktop%20Apps.md)를 참조하십시오. 관리되는 프로젝트에 리소스 파일 추가, 리소스 액세스, 정적 리소스 표시, 속성에 리소스 문자열 할당 등의 작업을 수동으로 수행하는 방법에 대한 자세한 내용은 [연습: Windows Forms 지역화](http://msdn.microsoft.com/ko-kr/9a96220d-a19b-4de0-9f48-01e5d82679e5) 및 [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)을 참조하십시오.  
  
 요구 사항  
  
 MFC  
  
## 참고 항목  
 [Controls in Dialog Boxes](../mfc/controls-in-dialog-boxes.md)   
 [컨트롤](../mfc/controls-mfc.md)