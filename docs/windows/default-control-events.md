---
title: "Default Control Events | Microsoft Docs"
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
  - "C++"
helpviewer_keywords: 
  - "Dialog editor, default control events"
  - "controls [C++], default control events"
  - "events [C++], controls"
  - "dialog box controls, events"
ms.assetid: 75556b23-18f5-4390-97a4-2ecad3309741
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Default Control Events
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

다음은 컨트롤 이름과 컨트롤을 사용하여 수행할 수 있는 기본 이벤트입니다.  
  
|컨트롤 이름|기본 이벤트|  
|------------|------------|  
|Animate|**ACN\_START**|  
|Check box|**BN\_CLICKED**|  
|Combo box|**CBN\_SELCHANGE**|  
|사용자 지정|**TTN\_GETDISPINFO**|  
|Date Time Picker|**DTN\_DATETIMECHANGE**|  
|입력란|**EN\_CHANGE**|  
|Group Box 컨트롤|적용할 수 없음|  
|Hot Key|**NM\_OUTOFMEMORY**|  
|IP 주소|**IPN\_FIELDCHANGED**|  
|List|**LVN\_ITEMCHANGE**|  
|목록 상자|**LBN\_SELCHANGE**|  
|Month Calendar|**MCN\_SELCHANGE**|  
|Picture 컨트롤|적용할 수 없음|  
|Progress|**NM\_CUSTOMDRAW**|  
|누름 단추|**BN\_CLICKED**|  
|Radio Button|**BN\_CLICKED**|  
|Rich Edit|**EN\_CHANGE**|  
|Scroll Bar|**NM\_THEMECHANGED**|  
|Slider|**NM\_CUSTOMDRAW**|  
|Spin|**UDN\_DELTAPOS**|  
|Static Text 컨트롤|적용할 수 없음|  
|Tab|**TCN\_SELCHANGE**|  
|트리|**TVN\_SELCHANGING**|  
  
 관리되는 프로젝트에 리소스를 추가하는 방법은 .NET Framework 개발자 가이드의 [응용 프로그램의 리소스](../Topic/Resources%20in%20Desktop%20Apps.md)를 참조하십시오. 관리되는 프로젝트에 리소스 파일 추가, 리소스 액세스, 정적 리소스 표시, 속성에 리소스 문자열 할당 등의 작업을 수동으로 수행하는 방법에 대한 자세한 내용은 [연습: Windows Forms 지역화](http://msdn.microsoft.com/ko-kr/9a96220d-a19b-4de0-9f48-01e5d82679e5) 및 [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)을 참조하십시오.  
  
## 요구 사항  
 Win32  
  
## 참고 항목  
 [Defining Member Variables for Dialog Controls](../mfc/defining-member-variables-for-dialog-controls.md)   
 [사용자 인터페이스 개체와 관련된 메시지 형식](../mfc/reference/message-types-associated-with-user-interface-objects.md)   
 [메시지 처리기 편집](../mfc/reference/editing-a-message-handler.md)   
 [리플렉트된 메시지의 메시지 처리기 정의](../mfc/reference/defining-a-message-handler-for-a-reflected-message.md)   
 [새 컨트롤 클래스 기반의 변수 선언](../mfc/reference/declaring-a-variable-based-on-your-new-control-class.md)   
 [가상 함수 재정의](../ide/overriding-a-virtual-function-visual-cpp.md)