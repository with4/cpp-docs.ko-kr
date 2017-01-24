---
title: "Introduction to ATL Window Classes | Microsoft Docs"
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
  - "window classes"
ms.assetid: 503efc2c-a269-495d-97cf-3fb300d52f3d
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Introduction to ATL Window Classes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

다음의 ATL 클래스를 구현 하 고 windows를 조작 하도록 설계 되었습니다.  
  
-   [CWindow](../atl/reference/cwindow-class.md) 창 핸들에 연결할 수 있는 `CWindow` 개체.  다음 호출 `CWindow` 창을 조작 하는 방법.  
  
-   [CWindowImpl](../atl/reference/cwindowimpl-class.md) 새 창을 구현 하 여 메시지를 메시지 맵 처리 합니다.  만들 수 있는 창을 새 Windows 클래스, 기존 클래스를 슈퍼 클래스 또는 서브 클래스에서 기존 창을 기준으로 합니다.  
  
-   [CDialogImpl](../atl/reference/cdialogimpl-class.md) 는 모달 또는 모덜리스 대화 상자 및 프로세스 메시지에 메시지 맵을 구현할 수 있습니다.  
  
-   [CContainedWindowT](../atl/reference/ccontainedwindowt-class.md) 해당 메시지 맵에 포함 되어 있는 창을 다른 클래스에서 구현 하는 미리 작성 된 클래스입니다.  사용 하 여 `CContainedWindowT` 클래스에 메시지 처리를 중앙 집중화할 수 있습니다.  
  
-   [CAxDialogImpl](../atl/reference/caxdialogimpl-class.md) ActiveX 컨트롤을 호스팅하는 대화 상자 \(모달 또는 모덜리스\)를 구현할 수 있습니다.  
  
-   [CSimpleDialog](../atl/reference/csimpledialog-class.md) 모달 대화 상자와 기본 기능을 구현할 수 있습니다.  
  
-   [CAxWindow](../atl/reference/caxwindow-class.md) ActiveX 컨트롤을 호스팅하는 창에 구현할 수 있습니다.  
  
-   [CAxWindow2T](../atl/reference/caxwindow2t-class.md) ActiveX 사용이 허가 된 컨트롤을 호스팅하는 창에 구현할 수 있습니다.  
  
 특정 창 클래스 외에 ATL 구현 ATL 창 개체를 보다 쉽게 디자인 하는 여러 클래스를 제공 합니다.  이러한 속성은 다음과 같습니다.  
  
-   [CWndClassInfo](../atl/reference/cwndclassinfo-class.md) 새 창 클래스의 정보를 관리 합니다.  
  
-   [용으로 CWinTraits](../atl/reference/cwintraits-class.md) 및  [CWinTraitsOR](../atl/reference/cwintraitsor-class.md) 의 표준화 성분 ATL 창 개체를 위한 간단한 메서드가 있습니다.  
  
## 참고 항목  
 [창 클래스](../atl/atl-window-classes.md)