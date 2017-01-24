---
title: "Toolbar Button Properties | Microsoft Docs"
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
  - "size, toolbar buttons"
  - "toolbar buttons (in Toolbar editor), setting properties"
  - "Toolbar editor, toolbar button properties"
  - "status bars, active toolbar button text"
  - "command IDs, toolbar buttons"
  - "width, toolbar buttons"
ms.assetid: b2705814-7c5d-4f24-8f77-07559b0cdda2
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Toolbar Button Properties
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

도구 모음 단추에는 다음과 같은 속성이 있습니다.  
  
|Property|설명|  
|--------------|--------|  
|**ID**|단추의 ID를 정의합니다.  드롭다운 목록에 일반적인 **ID** 이름이 있습니다.|  
|**너비**|단추의 너비를 설정합니다.  16 픽셀을 사용하는 것이 좋습니다.|  
|**높이**|단추의 높이를 설정합니다.  단추 하나의 높이를 변경하면 도구 모음에 있는 모든 단추의 높이가 변경됩니다.  15 픽셀을 사용하는 것이 좋습니다.|  
|**프롬프트**|상태 표시줄에 표시되는 메시지를 정의합니다.  \\n과 이름을 추가하면 도구 모음 단추에 도구 설명이 추가됩니다.  자세한 내용은 [도구 모음 단추에 대한 도구 설명 만들기](../mfc/creating-a-tool-tip-for-a-toolbar-button.md)를 참조하십시오.|  
  
 **Width** 및 **Height**는 모든 단추에 적용됩니다.  도구 모음을 만드는 데 사용되는 비트맵의 최대 너비는 2048입니다.  따라서 단추 너비를 512로 설정하면 단추를 네 개까지만 넣을 수 있고, 너비를 513으로 설정하면 세 개까지만 넣을 수 있습니다.  
  
 관리되는 프로젝트에 리소스를 추가하는 방법은 .NET Framework 개발자 가이드의 [응용 프로그램의 리소스](../Topic/Resources%20in%20Desktop%20Apps.md)를 참조하십시오. 관리되는 프로젝트에 리소스 파일 추가, 리소스 액세스, 정적 리소스 표시, 속성에 리소스 문자열 할당 등의 작업을 수동으로 수행하는 방법에 대한 자세한 내용은 [연습: Windows Forms 지역화](http://msdn.microsoft.com/ko-kr/9a96220d-a19b-4de0-9f48-01e5d82679e5) 및 [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)을 참조하십시오.  
  
## 요구 사항  
 MFC 또는 ATL  
  
## 참고 항목  
 [Changing the Properties of a Toolbar Button](../mfc/changing-the-properties-of-a-toolbar-button.md)   
 [Toolbar Editor](../mfc/toolbar-editor.md)