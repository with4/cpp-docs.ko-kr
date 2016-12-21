---
title: "메시지 맵(MFC) | Microsoft Docs"
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
  - "vc.mfc.messages"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "메시지 맵[C++], MFC"
  - "메시지[C++], Windows"
  - "MFC[C++], 메시지"
  - "Windows 메시지[C++], 메시지 맵"
ms.assetid: 3f9855e4-9d7d-4b64-8f3f-a19ea3cf79ba
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 메시지 맵(MFC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 참조의섹션은 모든 [메시지 매핑 매크로](../../mfc/reference/message-map-macros-mfc.md) 와 모든 [CWnd](../../mfc/reference/cwnd-class.md) 메세지 맵 앤트리를 해당 멤버 함수의 프로토타입과 함께 나열합니다.  
  
|범주|설명|  
|--------|--------|  
|[WM\_COMMAND 메시지 처리기](../../mfc/reference/wm-command-message-handler.md)|사용자 메뉴를 선택하거나 메뉴 선택키에 의해 생성 된 **WM\_COMMAND** 를 처리합니다.|  
|[자식 창 알림 메시지 처리기](../../mfc/reference/child-window-notification-message-handlers.md)|자식 창에서 알림 메시지를 처리 합니다.|  
|[WM 메시지 처리기](../../mfc/reference/handlers-for-wm-messages.md)|`WM_PAINT` 와 같은 **WM\_** 메세지를 처리합니다.|  
|[사용자 정의 메시지 처리기](../../mfc/reference/user-defined-handlers.md)|사용자 정의 메시지를 처리 합니다.|  
  
 \(이 참조에서 사용 되는 규칙 및 용어 설명에 대한 자세한 설명은 [메시지 맵 상호 참조를 사용 하는 방법](../../mfc/reference/how-to-use-the-message-map-cross-reference.md) 을 참조하십시오.\)  
  
 Windows는 메시지 기반 운영 체제이므로 Windows 환경에 대한 프로그래밍의 큰 부분은 메시지 처리를 포함해야합니다.  키 입력 또는 마우스 클릭과 같은 이벤트가 발생할 때마다, 이벤트를 처리해야 하는 응용 프로그램에 메시지를 보냅니다.  
  
 Microsoft 기반 클래스 라이브러리는 메시지 기반 프로그래밍을 위한 최적화된 프로그래밍 모델을 제공합니다.  이 모델에서 "메시지 맵" 함수는 특정한 클래스에 대해 어떤 함수가 다양한 메시지를 처리할지 지정됩니다.  메시지 맵은 어떠한 함수에의해 어떠한 메시지가 처리될지 지정하는 하나 이상의 매크로를 포함합니다.  예를 들어, `ON_COMMAND` 매크로를 포함하는 메시지 맵은 다음과 같아 보일 수 있습니다:  
  
 [!code-cpp[NVC_MFCMessageMaps#16](../../mfc/reference/codesnippet/CPP/message-maps-mfc_1.cpp)]  
  
 `ON_COMMAND` 매크로는 메뉴, 버튼, 액셀러레이터 키에 의해 생성된 명령 메시지를 처리하기 위해 사용됩니다.  [매크로](../../mfc/reference/message-map-macros-mfc.md) 는 다음과 같이 매핑할 수 있습니다.  
  
## Windows 메시지  
  
-   컨트롤 알림  
  
-   사용자 정의 메시지  
  
## 명령 메시지  
  
-   등록된 사용자 정의 메시지  
  
-   사용자 인터페이스 업데이트 메시지  
  
## 메시지의 범위  
  
-   명령  
  
-   업데이트 처리기 메시지  
  
-   컨트롤 알림  
  
 비록 메시지 맵 매크로가 중요하지만, 일반적으로는 반드시 그것을 직접 사용할 필요는 없습니다.  왜냐하면 메시지와 메시지 처리 함수를 연결할때 속성 창이 자동으로 소스 파일에 메시지 맵 엔트리를 생성하기 때문입니다.  속성 창을 이용하면 언제든지 메시지 맵 엔트리를 추가하고 수정할 수 있습니다.  
  
> [!NOTE]
>  속성 창은 메시지 맵 범위를 지원하지 않습니다.  이러한 메시지 맵 엔트리는 사용자가 직접 작성해야 합니다.  
  
 그러나 메시지 맵은 Microsoft 기반 클래스 라이브러리의 중요한 부분입니다.  따라서 메시지 맵이 무엇을 하고 그것을 위해 어떠한 설명서가 제공되는지 알아야 합니다.  
  
## 참고 항목  
 [구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)