---
title: "OLE 백그라운드 구현 전략 | Microsoft Docs"
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
  - "응용 프로그램[OLE], OLE 구현"
  - "OLE[C++], 개발 전략"
  - "OLE 응용 프로그램[C++], OLE 구현"
ms.assetid: 0875ddae-99df-488c-82c6-164074a81058
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# OLE 백그라운드 구현 전략
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

응용 프로그램에 따라, OLE 지원을 추가하는 것에 대한 네 가지 가능한 구현 전략이 있습니다.  
  
-   새 응용 프로그램을 작성하는 중입니다.  
  
     이 문제는 일반적으로 최소 작업을 필요로 합니다.  MFC 응용 프로그램 마법사를 실행 하고 고급 기능 또는 복합 문서 지원 기초 응용 프로그램 만들기를 선택 합니다.  이러한 옵션 및 용도에 대한 정보를 보려면 [Creating an MFC EXE Program](../mfc/reference/mfc-application-wizard.md) 를 참조하십시오.  
  
-   프로그램은 OLE를 지원하지 않는 Microsoft Foundation 클래스 라이브러리 버전 2.0 이상 또는 그 이상으로 작성되어야 합니다.  
  
     이전에 설명한 대로 MFC 응용 프로그램을 사용하여 새로운 응용 프로그램을 만들고, 코드를 새 응용 프로그램에서 기존 응용 프로그램으로 복사 붙여넣기 합니다.  이 것은 서버, 컨테이너 또는 자동화 된 응용 프로그램에 대해 작동 합니다.  이 계획의 예제는 MFC [SCRIBBLE](../top/visual-cpp-samples.md) 예제를 참조하십시오.  
  
-   OLE 1.0 버전 지원을 구현하는 MFC 라이브러리 프로그램을 가져야합니다.  
  
     이 변환 전략에 대해 [MFC Technical Note 41](../mfc/tn041-mfc-ole1-migration-to-mfc-ole-2.md) 를 참조하십시오.  
  
-   MFC를 사용하여 작성되지 않은 프로그램을 가지고 OLE 지원이 구현되거나 구현되지 않습니다.  
  
     이 경우에는 많은 작업이 필요합니다.  한 가지 방법은 첫째 전략과 같이 새 응용 프로그램 만들고 기존 코드를 새 응용 프로그램에 복사 붙여넣기 하는 것입니다.  C로 작성된 코드인 경우, 코드를 수정하여 C\+\+ 코드로 컴파일 될 수 있게 해야 합니다.  C 코드에서 Windows API를 호출 하는 경우 Microsoft Foundation 클래스를 사용 하도록 변경할 필요가 없습니다.  이 접근은 MFC의 2.0 버전 및 그 이상의 버전에서 사용되는 문서\/뷰 아키텍처를 지원하기 위해 프로그램의 재구성을 요구할 수도 있습니다.  이 아키텍처에 대한 자세한 내용은 [Technical Note 25](../mfc/tn025-document-view-and-frame-creation.md) 를 참조하십시오.  
  
 전략을 결정했으면, [Containers](../mfc/containers.md) 또는 [Servers](../mfc/servers.md) 를\(작성한 응용 프로그램의 형식에 따라\) 읽거나 샘플 프로그램을 시험해야 합니다.  MFC OLE 샘플 [OCLIENT](../top/visual-cpp-samples.md) 및 [HIERSVR](../top/visual-cpp-samples.md) 는 컨테이너 및 서버의 다양한 양상을 각각 구현하는 방법을 설명합니다.  이 문서 전반에 걸친 다양한 시점에서, 기술이 설명된 다양한 예제로서 이러한 샘플의 특정 함수를 참조할 수 있습니다.  
  
## 참고 항목  
 [OLE 백그라운드](../mfc/ole-background.md)   
 [컨테이너: 컨테이너 구현](../mfc/containers-implementing-a-container.md)   
 [서버: 서버 구현](../mfc/servers-implementing-a-server.md)   
 [MFC 응용 프로그램 마법사](../mfc/reference/mfc-application-wizard.md)