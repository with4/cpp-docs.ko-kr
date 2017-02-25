---
title: "이벤트 처리기 마법사 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
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
  - "이벤트 처리기 마법사[C++]"
ms.assetid: af8e1835-94b1-4d9a-b353-c519e011d3a1
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# 이벤트 처리기 마법사
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 마법사를 사용하면 대화 상자 컨트롤에 사용할 이벤트 처리기를 사용자가 선택한 클래스에 추가할 수 있습니다.  [속성 창](../Topic/Properties%20Window.md)에서 이벤트 처리기를 추가하면 대화 상자를 구현하는 클래스에만 이벤트 처리기를 추가할 수 있습니다.  자세한 내용은 [대화 상자 컨트롤에 사용할 이벤트 처리기 추가](../mfc/adding-event-handlers-for-dialog-box-controls.md)를 참조하십시오.  
  
 **명령 이름**  
 이벤트 처리기를 추가하기 위해 선택한 컨트롤을 나타냅니다.  이 상자는 사용할 수 없습니다.  
  
 **메시지 형식**  
 선택한 컨트롤에 대해 현재 사용할 수 있는 메시지 처리기의 목록을 표시합니다.  
  
 **함수 처리기 이름**  
 이벤트를 처리하기 위해 추가된 함수의 이름을 표시합니다.  기본적으로 이 이름은 메시지 유형과 명령을 기반으로 하며, 앞에 "On"이 붙습니다.  예를 들어, `IDC_BUTTON1`이라는 단추의 경우, 메시지 유형이 `BN_CLICKED`면 `OnBnClickedButton1`이라는 함수 처리기 이름이 표시됩니다.  
  
 **클래스 목록**  
 이벤트 처리기를 추가할 수 있는 클래스를 표시합니다.  선택한 대화 상자의 클래스는 빨간색으로 표시됩니다.  
  
 **처리기 설명**  
 **메시지 형식** 상자에서 선택된 항목에 대한 설명을 나타냅니다.  이 상자는 사용할 수 없습니다.  
  
 **추가 및 편집**  
 선택한 클래스나 개체에 메시지 처리기를 추가한 다음, 컨트롤 알림 처리기 코드를 추가할 수 있도록 해당 텍스트 편집기에서 새 함수를 엽니다.  
  
 **코드 편집**  
 컨트롤 알림 처리기 코드를 추가하거나 편집할 수 있도록 해당 텍스트 편집기에서 선택한 기존 함수를 엽니다.  
  
## 참고 항목  
 [이벤트 처리기 추가](../ide/adding-an-event-handler-visual-cpp.md)