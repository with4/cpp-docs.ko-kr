---
title: "Creating a Dialog Box That Users Cannot Exit | Microsoft Docs"
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
  - "dialog boxes, creating"
  - "modal dialog boxes, logon screens"
  - "logon screens"
ms.assetid: 54823c27-1658-4388-bd12-0a1ce8f3899e
caps.latest.revision: 12
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Creating a Dialog Box That Users Cannot Exit
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

사용자가 종료할 수 없는 런타임 대화 상자를 만들 수 있습니다. 이 종류의 대화 상자는 로그온에 유용하며, 응용 프로그램 또는 문서를 잠그는 데에도 유용합니다.  
  
### 사용자가 종료할 수 없는 대화 상자를 만들려면  
  
1.  대화 상자의 **속성** 창에서 **시스템 메뉴** 속성을 **false**로 설정합니다.  
  
     이렇게 하면 대화 상자의 시스템 메뉴 및 **닫기** 단추가 비활성화됩니다.  
  
2.  대화 상자 폼에서 **취소** 및 **확인** 단추를 삭제합니다.  
  
     런타임 시 사용자는 이러한 특징이 있는 모달 대화 상자를 종료할 수 없습니다.  
  
 이러한 종류의 대화 상자를 테스트할 수 있도록 테스트 대화 상자에는 ESC 키가 눌러지는 경우를 감지하는 기능이 있습니다. \(ESC는 VK\_ESCAPE 가상 키라고도 합니다.\) 런타임 시 대화 상자가 어떻게 동작하도록 설계되었는지와 관계없이 테스트 모드에서는 ESC 키를 누르면 대화 상자를 종료할 수 있습니다.  
  
> [!NOTE]
>  MFC 응용 프로그램의 경우 사용자가 종료할 수 없는 대화 상자를 만들려면 `OnOK`및 `OnCancel`의 기본 동작을 재정의해야 합니다. 관련된 단추를 삭제하더라도 Enter 또는 ESC 키를 누르면 여전히 대화 상자를 닫을 수 있기 때문입니다.  
  
 관리되는 프로젝트에 리소스를 추가하는 방법에 대한 자세한 내용은 [데스크톱 응용 프로그램의 리소스](../Topic/Resources%20in%20Desktop%20Apps.md) 항목을 참조하세요.  
  
## 요구 사항  
 Win32  
  
## 참고 항목  
 [How to: Create a Resource](../windows/how-to-create-a-resource.md)   
 [Resource Files](../mfc/resource-files-visual-studio.md)   
 [Dialog Editor](../mfc/dialog-editor.md)