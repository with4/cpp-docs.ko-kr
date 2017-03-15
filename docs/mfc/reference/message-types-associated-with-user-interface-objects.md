---
title: "사용자 인터페이스 개체와 관련된 메시지 형식 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.codewiz.uiobject.msgs"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "메시지 형식 및 사용자 인터페이스 개체"
ms.assetid: 681ee1a7-f6e6-4ea0-9fc6-1fb53a35516e
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# 사용자 인터페이스 개체와 관련된 메시지 형식
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

다음 표에서는 작업하는 개체 형식 및 해당 개체와 관련된 메시지 형식을 보여 줍니다.  
  
### 사용자 인터페이스 개체 및 관련된 메시지  
  
|개체 ID|메시지|  
|-----------|---------|  
|상위 창을 나타내는 클래스 이름|[CWnd](../../mfc/reference/cwnd-class.md) 파생 클래스\(대화 상자, 창, 자식 창, MDI 자식 창 또는 맨 위 프레임 창\)에 해당하는 Windows 메시지|  
|메뉴 또는 액셀러레이터 키 식별자|-   **COMMAND** 메시지\(프로그램 기능 실행\)<br />-   **UPDATE\_COMMAND\_UI** 메시지\(메뉴 항목 동적 업데이트\)|  
|컨트롤 식별자|선택된 컨트롤 형식에 대한 컨트롤 알림 메시지|  
  
## 참고 항목  
 [함수에 메시지 매핑](../../mfc/reference/mapping-messages-to-functions.md)   
 [코드 마법사로 기능 추가](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [클래스 추가](../../ide/adding-a-class-visual-cpp.md)   
 [멤버 함수 추가](../../ide/adding-a-member-function-visual-cpp.md)   
 [멤버 변수 추가](../../ide/adding-a-member-variable-visual-cpp.md)   
 [가상 함수 재정의](../../ide/overriding-a-virtual-function-visual-cpp.md)   
 [MFC 메시지 처리기](../../mfc/reference/adding-an-mfc-message-handler.md)   
 [클래스 구조 탐색](../../ide/navigating-the-class-structure-visual-cpp.md)