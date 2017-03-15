---
title: "MDI 탭 그룹 | Microsoft Docs"
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
  - "mdi, 탭 그룹"
  - "탭 그룹"
ms.assetid: 0a464f36-39b7-4e68-8b67-ec175de28377
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# MDI 탭 그룹
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

다중 문서 인터페이스\(MDI\) 탭된 그룹 기능은 MDI 클라이언트 영역에서 하나 이상의 탭된 창을 표시하기 위해 다중 문서 인터페이스\(MDI\) 응용 프로그램을 활성화 시킵니다. \(또는 *tabbed groups* 로 알려진 탭된 창의 그룹\)  탭된 창은 가로 또는 세로로 정렬할 수 있습니다.  하나 이상의 MDI 탭된 그룹을 호스트 하는 응용 프로그램은 그룹 분리기에 의해 구분 됩니다.  
  
## 기능  
 다음은 MDI 탭 그룹 기능입니다.  
  
-   응용 프로그램은 탭된 창을 동적으로 만들 수 있습니다.  
  
-   응용 프로그램은 탭된 창을 가로 또는 세로로 정렬할 수 있습니다.  
  
-   탭된 창의 그룹은 분할으로 구분 됩니다.  탭된 그룹 분할자를 사용 하여 조정할 수 있습니다.  
  
-   사용자 그룹 간에 개별 탭을 끌 수 있습니다.  
  
-   새 그룹을 만들려면 개별 탭을 끌 수 있습니다.  
  
-   사용자 탭을 이동 하거나 바로 가기 메뉴를 사용 하여 새 그룹을 만들 수 있습니다.  
  
-   응용 프로그램은 저장 하고 탭된 창의 레이아웃을 로드할 수 있습니다.  
  
-   응용 프로그램 저장 하고 MDI 문서 목록을 로드할 수 있습니다.  
  
-   응용 프로그램은 개별 탭된 그룹에 액세스 하고 해당 매개 변수를 수정할 수 있습니다.  
  
### 탭된 MDI그룹을 사용하여  
 다음은 MDI 탭 그룹을 사용 하여 일반적으로 수행 되는 작업입니다.  
  
-   메인 프레임 창에 대해 탭된 MDI 그룹을 활성화 하려면 [CMDIFrameWndEx::EnableMDITabbedGroups](../Topic/CMDIFrameWndEx::EnableMDITabbedGroups.md) 를 호출하십시오.  이 메서드의 두 번째 매개 변수는 `CMDITabInfo` 클래스의 인스턴스 입니다.  기본 매개 변수를 사용하거나 또는 `CMDIFrameWndEx::EnableMDITabbedGroups` 를 호출하기 전에 수정할 수 있습니다.  
  
-   탭된 MDI 그룹의 속성을 런타임에 수정하려면 `CMDITabInfo` 개체를 생성하거나 수정하고 `CMDIFrameWndEx::EnableMDITabbedGroups` 를 다시 호출하십시오.  
  
-   탭된 MDI 창의 목록을 얻으려면 `CMDIFrameWndEx::GetMDITabGroups` 을 호출하십시오.  
  
-   활성화된 탭된 그룹 다음에 새로운 탭된 MDI 그룹을 생성하려면 `CMDIFrameWndEx::MDITabNewGroup` 를 호출하십시오.  
  
-   입력 포커스를 이전 또는 다음 탭된 그룹의 창으로 이동하려면 `CMDIFrameWndEx::MDITabMoveToNextGroup` 를 호출하십시오.  
  
-   탭 그룹 통화 창이 MDI의 멤버 인지 여부를 확인 하려면`CMDIFrameWndEx::IsMemberOfMDITabGroup` 를 호출하십시오.  
  
-   MDI 탭 또는 탭된 MDI 그룹이 메인 프레임 창에 대해 활성 가능한 여부를 결정하려면 `CMDIFrameWndEx::AreMDITabs` 를 호출하십시오.  탭된 MDI 그룹이 활성화 가능한지 여부를 결정하려면 `CMDIFrameWndEx::IsMDITabbedGroup` 를 참조하십시오.  
  
-   `CMDIFrameWndEx` \- 파생 클래스에서 사용자가 탭 또는 다른 탭된 MDI 그룹을 드래그할 때 바로가기 메뉴를 표시하려면 `CMDIFrameWndEx::OnShowMDITabContextMenu` 를 재정의 하십시오.  이 메소드를 구현하지 않으면, 응용 프로그램은 바로 가기 메뉴를 표시하지 않습니다.  
  
-   호출 응용 프로그램에서 탭된 MDI 그룹의 레이아웃을 저장 하려면  `CMDIFrameWndEx::SaveMDIState`  를 호출하십시오.  이전에 저장된 탭된 MDI 그룹 프로필을 로드하려면 `CMDIFrameWndEx::LoadMDIState` 를 호출하십시오.  로드 또는 MDI 응용 프로그램에서 열려 있는 문서의 목록을 저장 하려면 이러한 메서드를 호출할 수 있습니다.  MDI 상태를 저장하고 로드하는 방법에 대한 자세한 내용은 [CMDIFrameWndEx::LoadMDIState](../Topic/CMDIFrameWndEx::LoadMDIState.md) 를 참조하십시오.  
  
## 참고 항목  
 [사용자 인터페이스 요소](../mfc/user-interface-elements-mfc.md)   
 [CMDIFrameWndEx 클래스](../mfc/reference/cmdiframewndex-class.md)   
 [CMDIChildWndEx 클래스](../mfc/reference/cmdichildwndex-class.md)   
 [CMDITabInfo Class](../mfc/reference/cmditabinfo-class.md)