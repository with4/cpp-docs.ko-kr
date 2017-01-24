---
title: "Implementing a Window with CWindowImpl | Microsoft Docs"
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
  - "CWindowImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL, windows"
  - "subclassing ATL window classes"
  - "superclassing, ATL"
  - "windows [C++], ATL"
  - "windows [C++], subclassing"
  - "windows [C++], superclassing"
ms.assetid: 3fc40550-f1d6-4702-8b7c-4cf682b6a855
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Implementing a Window with CWindowImpl
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

창을 구현 하는 클래스에서 파생 `CWindowImpl`.  파생된 클래스에서 메시지 맵과 메시지 처리기 함수를 선언 합니다.  이제 세 가지 방법으로 클래스를 사용할 수 있습니다.  
  
-   [새 Windows 클래스를 기반으로 창 만들기](#_atl_creating_a_window_based_on_a_new_windows_class)  
  
-   [기존 Windows 클래스를 슈퍼 클래스](#_atl_superclassing_an_existing_windows_class)  
  
-   [기존 창 서브 클래스](#_atl_subclassing_an_existing_window)  
  
##  <a name="_atl_creating_a_window_based_on_a_new_windows_class"></a> 새 Windows 클래스를 기반으로 창 만들기  
 `CWindowImpl`포함 된  [DECLARE\_WND\_CLASS](../Topic/DECLARE_WND_CLASS.md) Windows 클래스를 선언 하는 매크로.  이 매크로 구현 된 `GetWndClassInfo` 함수를 사용 하 여  [CWndClassInfo](../atl/reference/cwndclassinfo-class.md) 정보 새 Windows 클래스를 정의 합니다.  때 `CWindowImpl::Create` 이라고,이 Windows 클래스 등록 되지 및 새 창이 만들어집니다.  
  
> [!NOTE]
>  `CWindowImpl`전달  **NULL** 에 있는 `DECLARE_WND_CLASS` 매크로 ATL Windows 클래스 이름을 생성 합니다.  자신의 이름을 지정 하려면 문자열을 전달 `DECLARE_WND_CLASS` 에서 사용자 `CWindowImpl`\-클래스를 파생 합니다.  
  
## 예제  
 다음은 새 Windows 클래스를 기반으로 창을 구현 하는 클래스의 예입니다.  
  
 [!code-cpp[NVC_ATL_Windowing#64](../atl/codesnippet/CPP/implementing-a-window-with-cwindowimpl_1.h)]  
  
 창을 만들려면 인스턴스 만들기 `CMyWindow` 다음 호출에서  **만들기** 메서드.  
  
> [!NOTE]
>  기본 Windows 클래스 정보를 무시 하려면 구현에서 `GetWndClassInfo` 메서드를 설정 하 여 파생된 클래스에는 `CWndClassInfo` 멤버를 적절 한 값.  
  
##  <a name="_atl_superclassing_an_existing_windows_class"></a> 기존 Windows 클래스를 슈퍼 클 래 싱  
 [DECLARE\_WND\_SUPERCLASS](../Topic/DECLARE_WND_SUPERCLASS.md) 매크로 사용 하면 기존 Windows는 해당 수퍼 클래스는 창을 만들 수 클래스.  이 매크로에 지정 하면 `CWindowImpl`\-파생 클래스.  다른 ATL 창 처럼 메시지는 메시지 맵에서 처리 합니다.  
  
 사용 하는 경우 `DECLARE_WND_SUPERCLASS`, 새 Windows 클래스를 등록 합니다.  이 새 클래스는 기존 클래스를 지정 하지만 창 프로시저를 대체 합니다 수 `CWindowImpl::WindowProc` \(또는이 메서드를 재정의 하는 함수\).  
  
## 예제  
 다음 해당 수퍼 클래스 표준 편집 클래스의 예는 클래스:  
  
 [!code-cpp[NVC_ATL_Windowing#65](../atl/codesnippet/CPP/implementing-a-window-with-cwindowimpl_2.h)]  
  
 슈퍼 편집 창을 만들기 위해 인스턴스 만들기 `CMyEdit` 다음 호출에서  **만들기** 메서드.  
  
##  <a name="_atl_subclassing_an_existing_window"></a> 기존 창 서브클래싱  
 기존 창을 서브 클래스 하는 클래스에서 파생 `CWindowImpl` 하 고 앞의 두 경우와 같이 메시지 맵을 선언 합니다.  이미 기존 창을 서브 클래스를 것 이므로 Windows 클래스 정보를 지정 하지 않는 것 단.  
  
 대신 전화  **만들기**, 호출 `SubclassWindow` 하 고 서브클래싱하려면 원하는 기존 창 핸들을 전달 합니다.  창이 서브클래싱된 후 사용 `CWindowImpl::WindowProc` \(또는이 메서드를 재정의 하는 함수\) 메시지 맵에 메시지를 보내도록 합니다.  서브클래싱된 창의 개체 로부터 분리 하려면 호출 `UnsubclassWindow`.  다음은 창의 원래 창 프로시저를 복원 됩니다.  
  
## 참고 항목  
 [Implementing a Window](../atl/implementing-a-window.md)