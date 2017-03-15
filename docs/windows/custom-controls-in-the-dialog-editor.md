---
title: "Custom Controls in the Dialog Editor | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Custom Control"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "controls [C++], templates"
  - "custom controls [Visual Studio], dialog boxes"
  - "custom controls [Visual Studio]"
  - "dialog box controls, custom (user) controls"
  - "Dialog editor, custom controls"
ms.assetid: f494b314-4000-4bbe-bbd0-4b18fb71ede1
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Custom Controls in the Dialog Editor
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

대화 상자 편집기에서는 대화 상자 템플릿에 있는 기존 "사용자 지정" 컨트롤이나 "사용자" 컨트롤을 사용할 수 있습니다.  
  
> [!NOTE]
>  여기서 사용자 지정 컨트롤을 ActiveX 컨트롤과 혼동하면 안 됩니다.  ActiveX 컨트롤을 OLE 사용자 지정 컨트롤이라고도 합니다.  또한, 이 컨트롤을 Windows에서 사용자가 직접 그린 컨트롤과 혼동하지 마십시오.  
  
 이 기능을 사용하면 Windows에서 제공하지 않는 컨트롤을 사용할 수 있습니다.  실행할 때 컨트롤이 C\+\+ 클래스와 다른 창 클래스와 연결됩니다.  보다 일반적인 방법으로 동일한 작업을 수행하려면 대화 상자에 정적 컨트롤과 같은 컨트롤을 설치합니다.  그런 다음 실행할 때 [OnInitDialog](../Topic/CDialog::OnInitDialog.md) 함수에서 해당 컨트롤을 제거하고 자신의 사용자 지정 컨트롤을 대신 추가합니다.  
  
 이것은 오래된 기술입니다.  요즘은 대부분 ActiveX 컨트롤을 쓰거나 Windows 공용 컨트롤을 서브클래스하는 것이 좋습니다.  
  
 이러한 사용자 지정 컨트롤을 사용하면 다음과 같은 작업만 할 수 있습니다.  
  
-   대화 상자에서 위치 설정  
  
-   캡션 입력  
  
-   컨트롤의 Windows 클래스 이름 확인. 응용 프로그램 코드에서는 이 이름으로 컨트롤을 등록해야 합니다.  
  
-   컨트롤의 스타일을 설정하는 32비트 16진수 값 입력  
  
-   확장 스타일 설정  
  
 관리되는 프로젝트에 리소스를 추가하는 방법은 .NET Framework 개발자 가이드의 [응용 프로그램의 리소스](../Topic/Resources%20in%20Desktop%20Apps.md)를 참조하십시오. 관리되는 프로젝트에 리소스 파일 추가, 리소스 액세스, 정적 리소스 표시, 속성에 리소스 문자열 할당 등의 작업을 수동으로 수행하는 방법에 대한 자세한 내용은 [연습: Windows Forms 지역화](http://msdn.microsoft.com/ko-kr/9a96220d-a19b-4de0-9f48-01e5d82679e5) 및 [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)을 참조하십시오.  
  
## 요구 사항  
 Win32  
  
## 참고 항목  
 [Controls in Dialog Boxes](../mfc/controls-in-dialog-boxes.md)   
 [컨트롤](../mfc/controls-mfc.md)