---
title: "새 도구 모음 리소스 대화 상자 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.newtoolbarresource"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "새 도구 모음 리소스 대화 상자"
ms.assetid: 52dd01ad-e748-4ab2-b3eb-59f5df990ca6
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# 새 도구 모음 리소스 대화 상자
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

새 도구 모음 리소스 대화 상자를 사용하면 도구 모음 리소스에 추가하는 단추의 너비와 높이를 지정할 수 있습니다.  기본 크기는 16 × 15 픽셀입니다.  
  
 도구 모음을 만드는 데 사용되는 비트맵의 최대 너비는 2048입니다.  따라서 **단추 너비**를 512로 설정하면 단추를 네 개까지만 넣을 수 있습니다.  너비를 513으로 설정하면 단추를 세 개까지만 넣을 수 있습니다.  
  
 **단추 너비**  
 비트맵 리소스를 도구 모음 리소스로 변환할 때 도구 모음 단추의 너비를 이 입력란에 입력할 수 있습니다.  이미지 너비와 높이가 지정된 크기로 조정되고 색상은 표준 도구 모음 색상\(16 색상\)을 사용하도록 조정됩니다.  
  
 **단추 높이**  
 비트맵 리소스를 도구 모음 리소스로 변환할 때 도구 모음 단추의 높이를 이 입력란에 입력할 수 있습니다.  이미지 너비와 높이가 지정된 크기로 조정되고 색상은 표준 도구 모음 색상\(16 색상\)을 사용하도록 조정됩니다.  
  
 관리되는 프로젝트에 리소스를 추가하는 방법은 .NET Framework 개발자 가이드의 [응용 프로그램의 리소스](../Topic/Resources%20in%20Desktop%20Apps.md)를 참조하십시오. 관리되는 프로젝트에 리소스 파일 추가, 리소스 액세스, 정적 리소스 표시, 속성에 리소스 문자열 할당 등의 작업을 수동으로 수행하는 방법에 대한 자세한 내용은 [연습: Windows Forms 지역화](http://msdn.microsoft.com/ko-kr/9a96220d-a19b-4de0-9f48-01e5d82679e5) 및 [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)을 참조하십시오.  
  
## 요구 사항  
 MFC 또는 ATL  
  
## 참고 항목  
 [Toolbar Button Properties](../mfc/toolbar-button-properties.md)   
 [Converting Bitmaps to Toolbars](../mfc/converting-bitmaps-to-toolbars.md)   
 [Toolbar Editor](../mfc/toolbar-editor.md)