---
title: "Using IDispEventImpl | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDispEventImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IDispEventImpl class, using"
ms.assetid: 82d53b61-9d0d-45c5-aff9-2fafa468a9ca
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Using IDispEventImpl
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

사용 하는 경우 `IDispEventImpl` 이벤트를 처리 하도록 하면 됩니다.  
  
-   파생 클래스에서  [IDispEventImpl](../atl/reference/idispeventimpl-class.md).  
  
-   추가 된  [이벤트 싱크 맵](../Topic/BEGIN_SINK_MAP.md) 을 를 클래스.  
  
-   이벤트 싱크 맵을 사용 하려면 항목 추가  [SINK\_ENTRY](../Topic/SINK_ENTRY.md) 또는  [SINK\_ENTRY\_EX](../Topic/SINK_ENTRY_EX.md) 매크로.  
  
-   처리에 관심이 메서드를 구현 합니다.  
  
-   싱 및 이벤트 소스를 싱.  
  
## 예제  
 아래 예에서는 처리는  **DocumentChange** 이벤트가 Word에서  **응용 프로그램** 개체.  이 이벤트는 메서드로 정의 되어 있는  **ApplicationEvents** dispinterface를.  
  
 예제에서 되는  [ATLEventHandling 샘플에서](../top/visual-cpp-samples.md)는.  
  
 `[`  
  
 `uuid(000209F7-0000-0000-C000-000000000046),`  
  
 `hidden`  
  
 `]`  
  
 `dispinterface ApplicationEvents {`  
  
 `properties:`  
  
 `methods:`  
  
 `[id(0x00000001), restricted, hidden]`  
  
 `void Startup();`  
  
 `[id(0x00000002)]`  
  
 `void Quit();`  
  
 `[id(0x00000003)]`  
  
 `void DocumentChange();`  
  
 `};`  
  
 이 예제를 사용 하 여 `#import` Word의 형식 라이브러리에서 필요한 헤더 파일을 생성 합니다.  이 예제에서는 다른 버전의 Word 사용 하려면 올바른 mso dll 파일을 지정 해야 합니다.  예를 들어, Office 2000은 mso9.dll 제공 하 고 OfficeXP mso.dll을 제공 합니다.  이 코드는 stdafx.h에서 간단.  
  
 [!code-cpp[NVC_ATL_EventHandlingSample#1](../atl/codesnippet/CPP/using-idispeventimpl_1.h)]  
  
 다음 코드는 Notsosimple.h에 나타납니다.  관련 코드 주석으로 표시 됩니다.  
  
 [!code-cpp[NVC_ATL_EventHandlingSample#2](../atl/codesnippet/CPP/using-idispeventimpl_2.h)]  
  
## 참고 항목  
 [이벤트 처리](../atl/event-handling-and-atl.md)   
 [ATLEventHandling 샘플](../top/visual-cpp-samples.md)