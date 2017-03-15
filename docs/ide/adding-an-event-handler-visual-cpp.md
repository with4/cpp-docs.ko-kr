---
title: "이벤트 처리기 추가(Visual C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.codewiz.eventhandler.overview"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "이벤트 처리기, 추가"
  - "MSBuild, 속성"
  - "속성[Visual Studio], MSBuild"
ms.assetid: 050bebf0-a9e0-474b-905c-796fe5ac8fc3
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 이벤트 처리기 추가(Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

리소스 편집기에서 [이벤트 처리기 마법사](../ide/event-handler-wizard.md)를 사용하면 대화 상자 컨트롤에 사용하기 위해 새 이벤트 처리기를 추가하거나 기존 이벤트 처리기를 편집할 수 있습니다.  
  
 [속성 창](../Topic/Properties%20Window.md)에서 대화 상자를 구현하는 클래스에 이벤트를 추가할 수 있습니다.  대화 상자 클래스 이외의 클래스에 이벤트를 추가하려면 이벤트 처리기 마법사를 사용합니다.  
  
### 이벤트 처리기를 대화 상자 컨트롤에 추가하려면  
  
1.  [리소스 뷰](../windows/resource-view-window.md)에서 대화 상자 리소스를 두 번 클릭하여 컨트롤이 포함된 대화 상자 리소스를 [대화 상자 편집기](../mfc/dialog-editor.md)에서 엽니다.  
  
2.  알림 이벤트를 처리할 컨트롤을 마우스 오른쪽 단추로 클릭합니다.  
  
3.  바로 가기 메뉴에서 **이벤트 처리기 추가**를 클릭하여 이벤트 처리기 마법사를 표시합니다.  
  
4.  **메시지 형식** 상자에서 이벤트를 선택하여 **클래스 목록** 상자에서 선택한 클래스에 추가합니다.  
  
5.  **함수 처리기 이름** 상자의 기본 이름을 그대로 사용하거나 새 이름을 지정합니다.  
  
6.  **추가 및 편집**을 클릭하여 이벤트 처리기를 프로젝트에 추가하고 새 함수를 해당 텍스트 편집기에서 열어 적절한 이벤트 처리기 코드를 추가합니다.  
  
     선택된 메시지 유형에 선택된 클래스의 이벤트 처리기가 이미 있을 경우, **추가 및 편집**은 사용할 수 없지만 **코드 편집**은 사용할 수 있습니다.  **코드 편집**을 클릭하면 기존 함수가 해당 텍스트 편집기에 열립니다.  
  
 [속성 창](../Topic/Properties%20Window.md)에서 이벤트 처리기를 추가할 수도 있습니다.  자세한 내용은 [대화 상자 컨트롤에 사용할 이벤트 처리기 추가](../mfc/adding-event-handlers-for-dialog-box-controls.md)를 참조하십시오.  
  
## 참고 항목  
 [코드 마법사로 기능 추가](../ide/adding-functionality-with-code-wizards-cpp.md)   
 [클래스 추가](../ide/adding-a-class-visual-cpp.md)   
 [멤버 변수 추가](../ide/adding-a-member-variable-visual-cpp.md)   
 [멤버 함수 추가](../ide/adding-a-member-function-visual-cpp.md)   
 [MFC 메시지 처리기](../mfc/reference/adding-an-mfc-message-handler.md)   
 [클래스 구조 탐색](../ide/navigating-the-class-structure-visual-cpp.md)