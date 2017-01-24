---
title: "Adding Event Handlers for Dialog Box Controls | Microsoft Docs"
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
  - "Dialog editor, adding event handlers to controls"
  - "controls [C++], event handlers"
  - "dialog box controls, events"
  - "event handlers, for dialog box controls"
ms.assetid: f9c70f24-ea6f-44df-82eb-78a2deaee769
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Adding Event Handlers for Dialog Box Controls
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

클래스와 연결된 프로젝트 대화 상자의 경우에는 이벤트 처리기를 만들 때 몇 가지 바로 가기 메뉴를 사용할 수 있습니다.  따라서, 기본 컨트롤 알림 이벤트 처리기나 적용할 수 있는 Windows 메시지 처리기를 신속하게 만들 수 있습니다.  
  
#### 기본 컨트롤 알림 이벤트 처리기를 만들려면  
  
1.  컨트롤을 두 번 클릭합니다.  텍스트 편집기가 열립니다.  
  
2.  텍스트 편집기에서 컨트롤 알림 처리기 코드를 추가합니다.  
  
#### 적용할 수 있는 Windows 메시지 처리기를 만들려면  
  
1.  처리할 알림 이벤트의 컨트롤을 클릭합니다.  
  
2.  [속성 창](../Topic/Properties%20Window.md)에서 컨트롤과 연결된 Windows 공용 이벤트 목록을 표시하려면 **컨트롤 이벤트** 단추를 클릭합니다.  예를 들어, **정보** 대화 상자에서 표준 **확인** 단추를 누르면 다음과 같은 알림 이벤트가 표시됩니다.  
  
     **BN\_CLICKED**  
  
     **BN\_DOUBLECLICKED**  
  
     **BN\_KILLFOCUS**  
  
     **BN\_SETFOCUS**  
  
    > [!NOTE]
    >  아니면 대화 상자를 선택하고 **컨트롤 이벤트** 단추를 클릭합니다. 그러면 대화 상자의 모든 컨트롤에 대한 Windows 공용 이벤트 목록이 표시됩니다.  
  
3.  **속성** 창에서 처리할 이벤트 오른쪽에 있는 열을 클릭한 다음, 제안된 알림 이벤트 이름\(예: **OnBnClickedOK**는 **BN\_CLICKED**를 처리\)을 선택합니다.  
  
    > [!NOTE]
    >  기본 이벤트 처리기 이름을 선택하는 대신 원하는 이벤트 처리기 이름을 입력해도 됩니다.  
  
     이벤트를 선택하면 Visual Studio에서 텍스트 편집기가 열리고 이벤트 처리기의 코드가 표시됩니다.  예를 들어, 기본 **OnBnClickedOK**의 경우에는 다음 코드가 추가됩니다.  
  
    ```  
    void CAboutDlg::OnBnClickedOk(void)  
    {  
       // TODO: Add your control notification handler code here  
    }  
    ```  
  
 대화 상자 클래스 이외의 클래스에 이벤트 처리기를 추가하려면 [이벤트 처리기 마법사](../ide/event-handler-wizard.md)를 사용합니다.  자세한 내용은 [이벤트 처리기 추가](../ide/adding-an-event-handler-visual-cpp.md)를 참조하십시오.  
  
 관리되는 프로젝트에 리소스를 추가하는 방법은 .NET Framework 개발자 가이드의 [응용 프로그램의 리소스](../Topic/Resources%20in%20Desktop%20Apps.md)를 참조하십시오. 관리되는 프로젝트에 리소스 파일 추가, 리소스 액세스, 정적 리소스 표시, 속성에 리소스 문자열 할당 등의 작업을 수동으로 수행하는 방법에 대한 자세한 내용은 [연습: Windows Forms 지역화](http://msdn.microsoft.com/ko-kr/9a96220d-a19b-4de0-9f48-01e5d82679e5) 및 [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)을 참조하십시오.  
  
### 요구 사항  
 Win32  
  
## 참고 항목  
 [Default Control Events](../mfc/default-control-events.md)   
 [Defining Member Variables for Dialog Controls](../mfc/defining-member-variables-for-dialog-controls.md)   
 [대화 상자 컨트롤 및 변수 형식](../ide/dialog-box-controls-and-variable-types.md)   
 [클래스 추가](../ide/adding-a-class-visual-cpp.md)   
 [멤버 함수 추가](../ide/adding-a-member-function-visual-cpp.md)   
 [멤버 변수 추가](../ide/adding-a-member-variable-visual-cpp.md)   
 [가상 함수 재정의](../ide/overriding-a-virtual-function-visual-cpp.md)   
 [MFC 메시지 처리기](../mfc/reference/adding-an-mfc-message-handler.md)