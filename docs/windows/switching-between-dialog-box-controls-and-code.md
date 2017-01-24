---
title: "Switching Between Dialog Box Controls and Code | Microsoft Docs"
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
helpviewer_keywords: 
  - "events [C++], viewing for controls"
  - "Windows messages [C++], controls"
  - "messages [C++], viewing for dialog boxes"
  - "Dialog editor, accessing code"
  - "code [C++], switching from Dialog Editor"
  - "controls [C++], jumping to code"
  - "Dialog editor, switching between controls and code"
ms.assetid: 7da73815-b853-4203-ba45-bbe570695122
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Switching Between Dialog Box Controls and Code
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC 응용 프로그램에서 대화 상자 컨트롤을 두 번 클릭하면 처리기 코드로 이동하거나 스텁 처리기 기능을 신속하게 만들 수 있습니다.  
  
 컨트롤을 선택하고 [속성 창](../Topic/Properties%20Window.md)에서 **컨트롤 이벤트** 단추나 **메시지** 단추를 클릭하면 선택한 항목에 사용할 수 있는 전체 이벤트와 Windows 메시지 목록을 볼 수 있습니다.  목록에서 선택하여 처리기 기능을 만들거나 편집합니다.  
  
### 대화 상자 편집기에서 코드로 이동하려면  
  
1.  대화 상자 내의 컨트롤을 두 번 클릭하여 최근에 구현된 메시지 처리 기능에 대한 선언으로 이동합니다.  ATL 기반 대화 상자 클래스의 경우에는 항상 생성자 정의로 이동합니다.  
  
### 컨트롤의 이벤트를 보려면  
  
1.  컨트롤을 선택하고 [속성 창](../Topic/Properties%20Window.md)에서 **컨트롤 이벤트** 단추를 클릭합니다.  
  
    > [!NOTE]
    >  *대화 상자*에 포커스가 있을 때 **컨트롤 이벤트** 단추를 클릭하면 대화 상자의 모든 컨트롤 목록이 노출됩니다. 이 목록을 확장하면 각 컨트롤의 이벤트를 편집할 수 있습니다.  
  
     대화 상자에서 하나의 컨트롤에 포커스가 있을 때 이 컨트롤을 마우스 오른쪽 단추로 클릭하고 바로 가기 메뉴에서 **이벤트 처리기 추가**를 선택할 수 있습니다.  그러면 처리기가 추가될 클래스를 지정할 수 있습니다.  자세한 내용은 [이벤트 처리기 추가](../ide/adding-an-event-handler-visual-cpp.md)를 참조하십시오.  
  
### 대화 상자에 사용되는 메시지를 보려면  
  
1.  대화 상자를 선택하고 [속성 창](../Topic/Properties%20Window.md)에서 **메시지** 단추를 클릭합니다.  
  
 관리되는 프로젝트에 리소스를 추가하는 방법은 .NET Framework 개발자 가이드의 [응용 프로그램의 리소스](../Topic/Resources%20in%20Desktop%20Apps.md)를 참조하십시오. 관리되는 프로젝트에 리소스 파일 추가, 리소스 액세스, 정적 리소스 표시, 속성에 리소스 문자열 할당 등의 작업을 수동으로 수행하는 방법에 대한 자세한 내용은 [연습: Windows Forms 지역화](http://msdn.microsoft.com/ko-kr/9a96220d-a19b-4de0-9f48-01e5d82679e5) 및 [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)을 참조하십시오.  
  
 요구 사항  
  
 Win32  
  
## 참고 항목  
 [Dialog Editor](../mfc/dialog-editor.md)