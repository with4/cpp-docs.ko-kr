---
title: "창 개체 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
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
  - "프레임 창[C++], C++ 창 개체"
  - "HWND"
  - "HWND, 창 개체"
  - "메시지[C++], Windows"
  - "MFC[C++], windows"
  - "개체[C++], window"
  - "Visual C++, 창 개체"
  - "창 메시지[C++]"
  - "창 개체[C++]"
  - "창[C++], C++ 창 개체"
  - "Windows 창[C++]"
ms.assetid: 28b33ce2-af05-4617-9d03-1cb9a02be687
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 창 개체
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Mfc는 [CWnd](../mfc/reference/cwnd-class.md)을 제공해 창의  `HWND`  핸들을 캡슐화합니다.   `CWnd`  개체는 c \+ \+ 창 개체입니다. Windows 창을 나타내는  `HWND`  와는 다릅니다.   `CWnd` 을 사용하여 자신의 자식 창 파생 클래스에서 파생하거나,  `CWnd` 에서 파생된 MFC 클래스 중 하나를 사용합니다.  클래스  `CWnd` 는 프레임 창, 대화 상자, 자식 창, 컨트롤 및 도구 모음 등의 컨트롤 막대를 포함하는 모든 창에 대한 기본 클래스입니다.  [c \+ \+ 창 개체와 HWND의 관계](../mfc/relationship-between-a-cpp-window-object-and-an-hwnd.md)의 이해는 MFC 사용하여 효율적인 프로그래밍을 위해 중요합니다.  
  
 MFC에는 몇 가지 기본 기능 및 windows 관리를 제공합니다.  `CWnd` 로부터 클래스를 파생 시킬 수 있고 멤버 함수를 사용하여 제공된 기능을 사용자 지정할 수 있습니다.   `CWnd`  개체를 구성하고 [만들기](../Topic/CWnd::Create.md) 멤버 함수를 호출함으로써 자식 창을 생성할 수 있고, 그런다음   `CWnd`  멤버 함수을 사용해 자식 창을 사용자 지정할 수 있습니다.  프레임 창에서 폼뷰나 트리 뷰와 같은 [CView](../mfc/reference/cview-class.md)로부터 파생된 개체를 포함할 수 있습니다.  [CSplitterWnd](../mfc/reference/csplitterwnd-class.md) 클래스에서 제공하는 분할 창을 통해 문서의 여러가지 보기를 지원할 수 있습니다.  
  
 `CWnd`  클래스에서 파생된 각 개체는 Windows 메시지를 매핑할 수 있거나 사용자 지정 처리기에 Id를 명령할 수 있는 메시지 맵이 들어있습니다.  
  
 Windows 프로그래밍에 대한 일반 홍보 자료는  `HWND`  Api를 캡슐화하는  `CWnd`  멤버 함수를 사용하는 방법에 대해 공부하기 위한 훌륭한 리소스입니다.  
  
## CWnd에서 작동하는 함수  
 `CWnd` [파생된 창 클래스](../mfc/derived-window-classes.md) 는 생성자, 소멸자 및 멤버 함수 개체를 제공하여 개체를 초기화 하고 내부 Windows 구조를 만들고 캡슐화 된  `HWND` 에 접근할 수 있습니다.  `CWnd` 은 또한, 메시지를 보내는 윈도우의 상태에 액세스, 좌표 변환, 업데이트, 스크롤, 클립 보드에 액세스하고 기타 여러 작업을 위해 윈도우 API를 캡슐화하는 멤버 함수를 제공합니다.   `HWND`  인수를 사용하는 대부분의 Windows window 관리 Api는  `CWnd`  멤버 함수로 캡슐화됩니다.  함수와 매개 변수 이름은  `CWnd`  멤버 함수에서 유지됩니다.   `CWnd` 로 캡슐화 된 Windows Api에 대한 자세한 내용은 ,  [CWnd](../mfc/reference/cwnd-class.md) 클래스를 참조하십시오.  
  
## 창 메시지 및 CWnd  
 `CWnd` 의 주요 목적 중 하나는  `WM_PAINT`  또는  `WM_MOUSEMOVE`  같은 Windows 메시지를 처리 하기 위한 인터페이스를 제공 하는 것입니다.  대부분의  `CWnd`  멤버 함수는 표준 메시지에 대한 처리기입니다\- 이들은  `OnPaint`  및  **OnMouseMove**같은  **afx\_msg** 식별자 "On" 접두사로 시작합니다.  [메시지 처리 및 매핑](../mfc/message-handling-and-mapping.md)는  메시지와 메시지 처리에서 자세히 다룹니다.  프레임 워크의 창과 특수 목적을 위해 사용자가 직접 만든 사용자에 정보가 동일하게 적용됩니다.  
  
### 추가 정보  
  
-   [C\+\+ 창 개체와 HWND 간 관계](../mfc/relationship-between-a-cpp-window-object-and-an-hwnd.md)  
  
-   [파생된 창 클래스](../mfc/derived-window-classes.md)  
  
-   [창 만들기](../mfc/creating-windows.md)  
  
-   [창 개체 소멸시키기](../mfc/destroying-window-objects.md)  
  
-   [CWnd를 해당 HWND에서 분리](../mfc/detaching-a-cwnd-from-its-hwnd.md)  
  
-   [창 개체 작업](../mfc/working-with-window-objects.md)  
  
-   [디바이스 컨텍스트](../mfc/device-contexts.md): Windows 장치 그리기 독립화 개체  
  
-   [그래픽 개체](../mfc/graphic-objects.md): 펜, 브러시, 글꼴, 비트맵, 팔레트, 지역  
  
## 참고 항목  
 [Windows](../mfc/windows.md)