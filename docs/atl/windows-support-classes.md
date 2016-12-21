---
title: "Windows Support Classes | Microsoft Docs"
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
  - "vc.atl.windows"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL, windows"
  - "windows [C++], ATL"
ms.assetid: 750b14d5-d787-4d2b-9728-ac199ccad489
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Windows Support Classes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

다음 클래스에 대 한 windows 지원합니다.  
  
-   [\_U\_MENUorID](../atl/reference/u-menuorid-class.md) 에 대 한 래퍼를 제공 합니다.  **CreateWindow** 및  **즉, 개발자**.  
  
-   [CWindow](../atl/reference/cwindow-class.md) 창을 조작 하는 메서드가 포함 되어 있습니다.  `CWindow`은 `CWindowImpl`, `CDialogImpl` 및 `CContainedWindow`에 대한 기본 클래스입니다.  
  
-   [CWindowImpl](../atl/reference/cwindowimpl-class.md) 새 창 클래스를 기반으로 창을 구현 합니다.  또한 서브 클래스 또는 슈퍼 클래스에 창이 있습니다.  
  
-   [CDialogImpl](../atl/reference/cdialogimpl-class.md) 는 대화 상자를 구현 합니다.  
  
-   [CAxDialogImpl](../atl/reference/caxdialogimpl-class.md) ActiveX 컨트롤을 호스팅하는 대화 상자 \(모달 또는 모덜리스\)를 구현 합니다.  
  
-   [CSimpleDialog](../atl/reference/csimpledialog-class.md) \(모달 또는 모덜리스\) 대화 상자를 기본 기능을 구현 합니다.  
  
-   [CAxWindow](../atl/reference/caxwindow-class.md) ActiveX 컨트롤을 호스팅하는 창 조작 합니다.  
  
-   [CAxWindow2T](../atl/reference/caxwindow2t-class.md) 는 ActiveX 컨트롤을 호스트 하 고 또한 ActiveX 컨트롤 사용이 허가 된 호스팅을 지원 창을 조작 하기 위한 메서드를 제공 합니다.  
  
-   [CContainedWindowT](../atl/reference/ccontainedwindowt-class.md) 다른 개체에 포함 된 창을 구현 합니다.  
  
-   [CWndClassInfo](../atl/reference/cwndclassinfo-class.md) 새 창 클래스의 정보를 관리 합니다.  
  
-   [CDynamicChain](../atl/reference/cdynamicchain-class.md) 의 메시지 맵을 동적 체인을 지원 합니다.  
  
-   [CMessageMap](../atl/reference/cmessagemap-class.md) 허용 해당 메시지를 노출 하는 개체는 다른 개체에 매핑합니다.  
  
-   [용으로 CWinTraits](../atl/reference/cwintraits-class.md) 성분 ATL 창 개체의 표준화는 간단한 방법을 제공 합니다.  
  
-   [CWinTraitsOR](../atl/reference/cwintraitsor-class.md) 창 스타일과 확장된 스타일 창을 만드는 데 사용에 대 한 기본값을 제공 합니다.  창 만드는 동안 제공 되는 값에 논리적 OR 연산자를 사용 하 여이 값이 추가 됩니다.  
  
## 관련된 기사  
 [ATL 창 클래스](../atl/atl-window-classes.md)  
  
 [ATL 자습서](../atl/active-template-library-atl-tutorial.md)  
  
## 참고 항목  
 [Class Overview](../atl/atl-class-overview.md)   
 [Message Map Macros](../atl/reference/message-map-macros-atl.md)   
 [Window Class Macros](../atl/reference/window-class-macros.md)