---
title: "ActiveX 컨트롤 컨테이너 | Microsoft Docs"
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
  - "ActiveX 컨트롤 컨테이너[C++]"
  - "OLE 컨트롤[C++], 컨테이너"
ms.assetid: 0eb1a713-e607-4c79-a0c7-67c5f1fd5fab
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ActiveX 컨트롤 컨테이너
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ActiveX 컨트롤 컨테이너는 ActiveX 컨트롤을 완벽하게 지원하는 컨테이너고 그들을 그것의 창 또는 대화 상자에 통합시킬 수 있습니다.  ActiveX 컨트롤은 많은 개발 프로젝트에서 사용할 수 있는 재사용 가능한 소트프웨어 요소입니다.  컨트롤은 응용 프로그램의 사용자가 데이터베이스와 모니터 데이터에 접근할 수 있게 허용하고, 응용 프로그램 내에서 다양한 선택을 합니다.  ActiveX 컨트롤에 대한 자세한 내용은 [MFC ActiveX Controls](../mfc/mfc-activex-controls.md)을 참조하십시오.  
  
 컨트롤 컨테이너는 일반적으로 프로젝트에서 두 가지 형태를 취합니다.  
  
-   대화 상자에서 ActiveX 컨트롤이 사용되는 곳은 대화 상자 및 폼 뷰와 같은 대화 상자와 비슷한 창입니다.  
  
-   ActiveX에서 응용 프로그램 창은 툴바 또는 사용자 창의 다른 위치에서 사용됩니다.  
  
 ActiveX 컨트롤 컨테이너는 노출된 [methods](../mfc/mfc-activex-controls-methods.md) 및 [properities](../mfc/mfc-activex-controls-properties.md)를 경유한 컨트롤과 상호 작용합니다.  컨트롤 컨테이너에 의해 접근되거나 수정될 수 있는 이러한 방법과 속성은 ActiveX 컨트롤 컨테이너 프로젝트에서 래퍼 클래스를 통해 접근됩니다.  포함된 ActiveX 컨트롤은 또한 동작이 발생한 컨테이너를 통지하기 위해 [events](../mfc/mfc-activex-controls-events.md)를 전송하는 방법으로 컨테이너와 상호 작용할 수도 있습니다.  컨트롤 컨테이너는 이러한 알림에 의거하여 작업하는 것을 선택하거나 그렇지 않을 수 있습니다.  
  
 추가 문서는 ActiveX 컨트롤 컨테이너 프로젝트에서 시작하여 Visual C\+\+을 사용하여 만든 ActiveX 컨트롤 컨테이너와 관련 있는 기본 구현 문제까지에 대한 몇 가지 주제에 대해 설명합니다.  
  
-   [MFC ActiveX 컨트롤 컨테이너 만들기](../mfc/reference/creating-an-mfc-activex-control-container.md)  
  
-   [ActiveX 컨트롤에 대한 컨테이너](../mfc/containers-for-activex-controls.md)  
  
-   [ActiveX 컨트롤 컨테이너: ActiveX 컨트롤 포함 수동 설정](../mfc/activex-control-containers-manually-enabling-activex-control-containment.md)  
  
-   [ActiveX 컨트롤 컨테이너: 컨트롤 컨테이너 응용 프로그램에 컨트롤 삽입](../mfc/inserting-a-control-into-a-control-container-application.md)  
  
-   [ActiveX 컨트롤 컨테이너: ActiveX 컨트롤을 멤버 변수에 연결](../mfc/activex-control-containers-connecting-an-activex-control-to-a-member-variable.md)  
  
-   [ActiveX 컨트롤 컨테이너: ActiveX 컨트롤에서 보낸 이벤트 처리](../mfc/activex-control-containers-handling-events-from-an-activex-control.md)  
  
-   [ActiveX 컨트롤 컨테이너: 컨트롤 속성 보기 및 수정](../mfc/activex-control-containers-viewing-and-modifying-control-properties.md)  
  
-   [ActiveX 컨트롤 컨테이너: ActiveX 컨트롤 컨테이너에서 ActiveX 컨트롤 프로그래밍](../mfc/programming-activex-controls-in-a-activex-control-container.md)  
  
-   [ActiveX 컨트롤 컨테이너: 대화 상자가 아닌 컨테이너에서 컨트롤 사용](../mfc/activex-control-containers-using-controls-in-a-non-dialog-container.md)  
  
 대화 상자에서 ActiveX 컨트롤 사용에 대한 자세한 내용은 [Dialog Editor](../mfc/dialog-editor.md)을 참조하세요.  
  
 Visual C\+\+와 MFC ActiveX 컨트롤 클래스를 사용한 ActiveX 컨트롤 개발의 세부 정보를 설명하는 문서 목록은, [MFC ActiveX controls](../mfc/mfc-activex-controls.md)을 참조하십시오.  항목은 기능 범주별로 그룹화 됩니다.  
  
## 참고 항목  
 [MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)