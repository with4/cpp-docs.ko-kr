---
title: "Creating New Toolbars | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.toolbar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "toolbars [C++], creating"
  - "Toolbar editor, creating new toolbars"
  - "Insert Resource"
ms.assetid: 1b28264b-0718-4df8-9f65-979805d2efef
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Creating New Toolbars
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

### 새 도구 모음을 만들려면  
  
1.  **리소스** 뷰에서 마우스 오른쪽 단추로 .rc 파일을 클릭하고 바로 가기 메뉴에서 **리소스 추가**를 선택합니다.  .rc 파일에 기존 도구 모음이 있으면 마우스 오른쪽 단추로 **도구 모음** 폴더를 클릭하고 바로 가기 메뉴에서 **도구 모음 삽입**을 선택합니다.  
  
     **참고** 프로젝트에 .rc 파일이 없으면 [새 리소스 스크립트 파일 만들기](../windows/how-to-create-a-resource-script-file.md)를 참조하십시오.  
  
2.  **리소스 추가** 대화 상자의 **리소스 형식** 목록에서 **도구 모음**을 선택하고 **새로 만들기**를 클릭합니다.  
  
     **도구 모음** 리소스 형식 옆에 더하기 기호\(\+\)가 나타나면 도구 모음 템플릿을 사용할 수 있습니다.  더하기 기호\(\+\)를 클릭하여 템플릿 목록을 확장하고 템플릿을 선택한 다음 **새로 만들기**를 클릭합니다.  
  
     \-또는\-  
  
3.  [기존 비트맵을 도구 모음으로 변환](../mfc/converting-bitmaps-to-toolbars.md)합니다.  
  
 관리되는 프로젝트에 리소스를 추가하는 방법은 .NET Framework 개발자 가이드의 [응용 프로그램의 리소스](../Topic/Resources%20in%20Desktop%20Apps.md)를 참조하십시오. 관리되는 프로젝트에 리소스 파일 추가, 리소스 액세스, 정적 리소스 표시, 속성에 리소스 문자열 할당 등의 작업을 수동으로 수행하는 방법에 대한 자세한 내용은 [연습: Windows Forms 지역화](http://msdn.microsoft.com/ko-kr/9a96220d-a19b-4de0-9f48-01e5d82679e5) 및 [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)을 참조하십시오.  
  
 요구 사항  
  
 MFC 또는 ATL  
  
## 참고 항목  
 [Toolbar Editor](../mfc/toolbar-editor.md)