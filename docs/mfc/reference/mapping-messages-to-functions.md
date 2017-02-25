---
title: "함수에 메시지 매핑 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.codewiz.mapping.msg.function"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "메시지 맵[C++], 함수에 메시지 매핑"
  - "Windows 메시지[C++], 메시지 처리기 추가"
ms.assetid: a7727a62-f638-4b20-b7f5-131f47200d6a
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# 함수에 메시지 매핑
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

속성 창을 사용하면 메시지 처리기\(MFC 사용자 인터페이스 클래스의 멤버 함수\)를 응용 프로그램 리소스에서 만든 메시지에 바인딩할 수 있습니다.  메시지 처리기에서는 [MFC 메시지 맵](../../mfc/messages-and-commands-in-the-framework.md)을 사용하여 바인딩을 만듭니다.  
  
 클래스 뷰를 사용하여 프레임워크 클래스 중 하나에서 파생된 새 클래스를 만들 경우 지정한 헤더 파일\(.h\)과 구현 파일\(.cpp\)에 완전한 기능적 클래스가 자동으로 배치됩니다.  
  
> [!NOTE]
>  메시지를 처리하지 않는 클래스를 새로 추가하려면 텍스트 편집기에서 직접 클래스를 만듭니다.  
  
### 속성 창을 사용하여 메시지 처리기를 정의하거나 제거하려면  
  
1.  클래스 뷰에서 클래스를 클릭합니다.  
  
2.  속성 창에서 **메시지** 단추를 클릭합니다.  
  
    > [!NOTE]
    >  클래스 뷰에서 클래스 이름을 선택하거나 소스 창 안에서 클래스 이름을 클릭하면 **메시지** 단추를 사용할 수 있습니다.  
  
     프로젝트에 메시지 처리기가 있으면 메시지 오른쪽 열에 처리기 이름이 표시됩니다.  
  
3.  If the message has no handler, then click the cell in the right column in the Properties window to display the suggested name of the handler as \<add\>*HandlerName*. \(For example, the `WM_TIMER` message handler suggests \<add\>`OnTimer`\).  
  
4.  제안된 이름을 클릭하여 함수의 스텁 코드를 추가합니다.  
  
5.  메시지 처리기를 편집하려면 클래스 뷰에서 메시지를 두 번 클릭한 다음 소스 창에서 코드를 편집합니다.  
  
 To remove a message handler, double\-click the handler in the right column and select \<delete\>*HandlerName*.  함수 코드는 주석 처리됩니다.  
  
## 참고 항목  
 [MFC 메시지 처리기](../../mfc/reference/adding-an-mfc-message-handler.md)   
 [코드 마법사로 기능 추가](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [클래스 추가](../../ide/adding-a-class-visual-cpp.md)   
 [멤버 함수 추가](../../ide/adding-a-member-function-visual-cpp.md)   
 [멤버 변수 추가](../../ide/adding-a-member-variable-visual-cpp.md)   
 [가상 함수 재정의](../../ide/overriding-a-virtual-function-visual-cpp.md)   
 [Adding Event Handlers for Dialog Box Controls](../../mfc/adding-event-handlers-for-dialog-box-controls.md)   
 [클래스 구조 탐색](../../ide/navigating-the-class-structure-visual-cpp.md)