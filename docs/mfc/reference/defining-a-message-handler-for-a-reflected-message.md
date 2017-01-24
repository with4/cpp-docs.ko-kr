---
title: "리플렉트된 메시지의 메시지 처리기 정의 | Microsoft Docs"
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
  - "vc.codewiz.defining.msg.msghandler"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "메시지 처리, 리플렉트된 메시지"
  - "메시지, 리플렉트됨"
ms.assetid: 5a403528-58c5-46e7-90d5-4a77f0ab9b9c
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 리플렉트된 메시지의 메시지 처리기 정의
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

MFC 컨트롤 클래스를 새로 만들었으면 이 클래스에 대한 메시지 처리기를 정의할 수 있습니다.  리플렉트된 메시지 처리기를 사용하면 부모 창에서 메시지를 받기 전에 컨트롤 클래스가 자체 메시지를 처리할 수 있습니다.  MFC [CWnd::SendMessage](../Topic/CWnd::SendMessage.md) 함수를 사용하여 컨트롤에서 부모 창으로 메시지를 보낼 수 있습니다.  
  
 예를 들어, 이 기능을 사용하면 부모 창에 의존하기 보다는 스스로 다시 그리는\(소유자 그리기\) 목록 상자를 만들 수 있습니다.  리플렉팅된 메시지에 대한 자세한 내용은 [리플렉션된 메시지 처리](../../mfc/handling-reflected-messages.md)를 참조하십시오.  
  
 같은 기능을 가지는 [ActiveX 컨트롤](../../mfc/activex-controls-on-the-internet.md)을 만들려면 ActiveX 컨트롤에 대한 프로젝트를 만들어야 합니다.  
  
> [!NOTE]
>  아래에서 설명한 대로 속성 창을 사용하여 ActiveX 컨트롤에 대해 리플렉트된 메시지\(OCM\_*Message*\)를 추가할 수 없습니다.  이 메시지는 수동으로 추가해야 합니다.  
  
### 속성 창에서 리플렉트된 메시지의 메시지 처리기를 정의하려면  
  
1.  목록, rebar 컨트롤, 도구 모음, tree 컨트롤 등과 같은 컨트롤을 MFC 프로젝트에 추가합니다.  
  
2.  클래스 뷰에서 컨트롤 클래스 이름을 클릭합니다.  
  
3.  [속성 창](../Topic/Properties%20Window.md)의 **클래스 이름** 목록에 해당 컨트롤 클래스 이름이 표시됩니다.  
  
4.  **메시지** 단추를 클릭하여 컨트롤에 추가할 수 있는 Windows 메시지를 표시합니다.  
  
5.  **리플렉션** 머리글이 표시될 때까지 속성 창에서 메시지 목록을 아래로 스크롤합니다.  또는 **범주** 단추를 클릭한 다음 뷰를 축소하여 **리플렉션** 머리글을 봅니다.  
  
6.  처리기를 정의할 리플렉트된 메시지를 선택합니다.  리플렉트된 메시지에는 등호\(\=\)가 붙습니다.  
  
7.  Click the cell in the right column in the Properties window to display the suggested name of the handler as \<add\>*HandlerName*. \(For example, the **\=WM\_CTLCOLOR** message handler suggests \<add\>**CtlColor**\).  
  
8.  사용하려는 제안된 이름을 클릭합니다.  처리기가 프로젝트에 추가됩니다.  
  
     추가한 메시지 처리기 이름이 리플렉트된 메시지 창의 오른쪽 열에 나타납니다.  
  
9. 메시지 처리기를 편집하거나 삭제하려면 4\-7단계를 반복합니다.  편집하거나 삭제할 처리기 이름이 포함된 셀을 클릭한 다음 해당 작업을 클릭합니다.  
  
## 참고 항목  
 [함수에 메시지 매핑](../../mfc/reference/mapping-messages-to-functions.md)   
 [코드 마법사로 기능 추가](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [클래스 추가](../../ide/adding-a-class-visual-cpp.md)   
 [멤버 함수 추가](../../ide/adding-a-member-function-visual-cpp.md)   
 [멤버 변수 추가](../../ide/adding-a-member-variable-visual-cpp.md)   
 [가상 함수 재정의](../../ide/overriding-a-virtual-function-visual-cpp.md)   
 [MFC 메시지 처리기](../../mfc/reference/adding-an-mfc-message-handler.md)   
 [클래스 구조 탐색](../../ide/navigating-the-class-structure-visual-cpp.md)