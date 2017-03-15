---
title: "Specifying the Location and Size of a Dialog Box | Microsoft Docs"
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
  - "dialog boxes, size"
  - "dialog boxes, positioning"
ms.assetid: 2b7c495e-6595-4cfb-9664-80b2826d0851
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Specifying the Location and Size of a Dialog Box
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

대화 상자의 위치와 크기뿐 아니라 대화 상자 안에 있는 컨트롤의 위치와 크기도 대화 상자 단위로 측정됩니다.  컨트롤과 대화 상자를 선택하면 Visual Studio의 오른쪽 아래 상태 표시줄에 컨트롤과 대화 상자의 값이 표시됩니다.  
  
 [속성 창](../Topic/Properties%20Window.md)에서 세 가지 속성을 설정하여 화면 상에서의 대화 상자 위치를 지정할 수 있습니다.  Center 속성은 부울 값이며, 이 값을 True로 설정하면 대화 상자가 화면 가운데에 표시됩니다.  이 값을 False로 설정하면 XPo와 YPos 속성을 설정하여 화면에서 대화 상자를 표시할 위치를 명시적으로 지정할 수 있습니다.  위치 속성은 보이는 영역의 왼쪽 위 모퉁이부터 계산한 오프셋 값이며, {X\=0, Y\=0}과 같이 지정됩니다.  위치는 **Absolute Align** 속성을 기반으로 합니다. 이 속성이 True이면 화면을 기준으로 한 좌표를 사용하고 False이면 대화 상자 사용자의 창을 기준으로 합니다.  
  
 관리되는 프로젝트에 리소스를 추가하는 방법은 .NET Framework 개발자 가이드의 [응용 프로그램의 리소스](../Topic/Resources%20in%20Desktop%20Apps.md)를 참조하십시오. 관리되는 프로젝트에 리소스 파일 추가, 리소스 액세스, 정적 리소스 표시, 속성에 리소스 문자열 할당 등의 작업을 수동으로 수행하는 방법에 대한 자세한 내용은 [연습: Windows Forms 지역화](http://msdn.microsoft.com/ko-kr/9a96220d-a19b-4de0-9f48-01e5d82679e5) 및 [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)을 참조하십시오.  
  
## 요구 사항  
 Win32  
  
## 참고 항목  
 [Controls in Dialog Boxes](../mfc/controls-in-dialog-boxes.md)   
 [컨트롤](../mfc/controls-mfc.md)