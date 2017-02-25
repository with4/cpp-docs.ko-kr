---
title: "Defining Member Variables for Dialog Controls | Microsoft Docs"
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
  - "member variables, defining for controls"
  - "variables, dialog box control member variables"
  - "controls [C++], member variables"
  - "Dialog editor, defining member variables for controls"
ms.assetid: 84347c63-c33c-4b04-91f5-6d008c45ba58
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Defining Member Variables for Dialog Controls
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

단추를 제외한 대화 상자 컨트롤에 대해 멤버 변수를 정의하려면 다음 메서드를 사용할 수 있습니다.  
  
> [!NOTE]
>  이 항목은 MFC 프로젝트 내의 대화 상자 컨트롤에만 적용됩니다.  ATL 프로젝트는 **새 Windows 메시지 및 이벤트 처리기** 대화 상자를 사용합니다.  
  
### \(단추 이외의\) 대화 상자 컨트롤에 대해 멤버 변수를 정의하려면  
  
1.  [대화 상자 편집기](../mfc/dialog-editor.md)에서 컨트롤을 선택합니다.  
  
2.  **CTRL** 키를 누른 채 대화 상자 컨트롤을 두 번 클릭합니다.  
  
     [멤버 변수 추가 마법사](../ide/add-member-variable-wizard.md)가 나타납니다.  
  
3.  **멤버 변수 추가** 마법사에 적절한 정보를 입력합니다.  자세한 내용은 [대화 상자 데이터 교환](../mfc/dialog-data-exchange.md)을 참조하세요.  
  
4.  **확인**을 클릭하여 대화 상자 편집기로 돌아갑니다.  
  
    > [!TIP]
    >  대화 상자 컨트롤에서 기존 처리기로 이동하려면 컨트롤을 두 번 클릭합니다.  
  
 관리되는 프로젝트에 리소스를 추가하는 방법은 .NET Framework 개발자 가이드의 [응용 프로그램의 리소스](../Topic/Resources%20in%20Desktop%20Apps.md)를 참조하세요. 관리되는 프로젝트에 리소스 파일 추가, 리소스 액세스, 정적 리소스 표시, 속성에 리소스 문자열 할당 등의 작업을 수동으로 수행하는 방법에 대한 자세한 내용은 [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)을 참조하세요.  
  
 **MFC 클래스 마법사**의 **멤버 변수** 탭을 사용하여 지정 클래스에 대한 새 멤버 변수를 추가하고 이미 정의된 변수를 볼 수도 있습니다.  
  
 요구 사항  
  
 MFC  
  
## 참고 항목  
 [함수에 메시지 매핑](../mfc/reference/mapping-messages-to-functions.md)   
 [코드 마법사로 기능 추가](../ide/adding-functionality-with-code-wizards-cpp.md)   
 [MFC 클래스 마법사](../mfc/reference/mfc-class-wizard.md)   
 [클래스 추가](../ide/adding-a-class-visual-cpp.md)   
 [멤버 함수 추가](../ide/adding-a-member-function-visual-cpp.md)   
 [멤버 변수 추가](../ide/adding-a-member-variable-visual-cpp.md)   
 [가상 함수 재정의](../ide/overriding-a-virtual-function-visual-cpp.md)   
 [MFC 메시지 처리기](../mfc/reference/adding-an-mfc-message-handler.md)