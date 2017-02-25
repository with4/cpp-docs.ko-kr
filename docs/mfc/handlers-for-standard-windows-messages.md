---
title: "표준 Windows 메시지에 대한 처리기 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "afx_msg"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "함수[C++], 처리기"
  - "처리기 함수, 표준 Windows 메시지"
  - "메시지 처리[C++], Windows 메시지 처리기"
  - "메시지[C++], Windows"
  - "Windows 메시지[C++], 처리기"
ms.assetid: 19412a8b-2c38-4502-81da-13c823c7e36c
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# 표준 Windows 메시지에 대한 처리기
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

표준 Windows 메시지\(**WM\_**\)에 대한 기본 처리기는 `CWnd`에서 미리 정의되었습니다.  클래스 라이브러리는 메시지 이름의 처리기들에 대한 이름을 기반으로 합니다.  예를 들어, `WM_PAINT` 메시지에 대한 처리기는  `CWnd` 에 선언됩니다:  
  
 `afx_msg void OnPaint();`  
  
 **afx\_msg** 키워드는 `CWnd` 멤버 함수들로 부터 처리기를 구분하여 c\+\+ **가상**키워드의 효과를 제안합니다.  단, 이러한 함수들은 실제로 가상이 아닌 메시지 맵을 통해 구현 됩니다.  메시지 맵은 c \+ \+ 언어에 대 한 확장이 아닌 표준 전처리기 매크로에 따라 달라 집니다.  **afx\_msg** 키워드는 전처리 후 빈 공간을 확인 합니다.  
  
 기본 클래스에 정의 된 처리기를 재정의 하려면 파생된 클래스에 동일한 프로토타입을 사용하여 함수를 간단하게 정의하고 처리기에 대한 메시지 맵 엔트리를 만듭니다.  사용자의 처리기 "재정의" 사용자 클래스의 기본 클래스의 같은 이름의 처리기  
  
 몇몇 경우에 처리기는 기본 클래스의 재정의 된 처리기를 호출해야하고 그러면 기본 클래스와 Windows는 메시지에서 작동할 수 있습니다.  재정의에서 기본 클래스 처리기를 호출 하는 곳은 상황에 따라 달라 집니다.  때로는 먼저 기본 클래스 처리기를 호출 하 고 때로는 마지막 해야 합니다.  만약 사용자가 메시지를 직접 처리 하지 않도록 선택한다면 때로는 사용자가 조건에 따라 기본 클래스 처리기를 호출합니다.  때로는 사용자가 기본 클래스 처리기를 호출하고 기본 클래스 처리기에 의해 반환되는 값이나 상태에 따라 사용자의 처리기 코드를 실행합니다.  
  
> [!CAUTION]
>  만약 사용자가 기본 클래스 처리기에 그것들을 전달하려고 한다면 처리기에 전달된 인수들을 수정하는 것은 안전하지 않습니다.  예를 들어, `OnChar`처리기의 `nChar` 인수를 수정하려고  합니다. \(예를들어 대문자로\)  이 동작은 매우 불분명하지만 만약 사용자가 이 효과를 수행해야 할 경우 **SendMessage** 대신 `CWnd` 멤버 함수를 사용하십시오.  
  
 주어진 메시지를 재정의하는 적절 한 방법을 어떻게 알 수 있을까요?  속성 창이 주어진 메시지에 대해 처리기 함수의 기초를 작성할 때 `WM_CREATE`에 대한 `OnCreate` 처리기, 예를 들어 그것은 권장된 재정의 멤버 함수의 형태로 스케치합니다.  다음 예제에서는 처리기가 기본 클래스 처리기를 먼저 호출하고 \-1을 반환하지 않는 조건에서만 진행하기를 권장합니다.  
  
 [!code-cpp[NVC_MFCMessageHandling#3](../mfc/codesnippet/CPP/handlers-for-standard-windows-messages_1.cpp)]  
  
 일반적으로 이 처리기의 이름은 접두사 "On"으로 시작합니다. 이러한 처리기 중 일부가 인수가 없지만 다른 것은 여러 개를 갖습니다.  일부도 `void`보다 다른 반환 형식을 갖습니다.  모든 **WM\_**메시지들에 대한 기본 처리기들은 "On"으로 시작하는 이름의 `CWnd` 클래스의 멤버 함수들과 같은 *MFC 참조*에 설명되어있습니다. `CWnd`에서 멤버 함수 선언들은 접두사가 **afx\_msg**로 이미 고정되어 있습니다.  
  
## 참고 항목  
 [메시지 처리기 함수 선언](../mfc/declaring-message-handler-functions.md)