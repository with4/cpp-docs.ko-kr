---
title: "Using IDispEventSimpleImpl | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDispEventSimpleImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IDispEventSimpleImpl class, using"
ms.assetid: 8640ad1a-4bd0-40a5-b5e4-7322685d7aab
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Using IDispEventSimpleImpl
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

사용 하는 경우 `IDispEventSimpleImpl` 이벤트를 처리 하도록 하면 됩니다.  
  
-   파생 클래스에서  [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md).  
  
-   추가 된  [이벤트 싱크 맵](../Topic/BEGIN_SINK_MAP.md) 을 를 클래스.  
  
-   정의  [\_ATL\_FUNC\_INFO](../atl/reference/atl-func-info-structure.md) 이벤트를 설명 하는 구조입니다.  
  
-   이벤트 싱크 맵을 사용 하려면 항목 추가  [SINK\_ENTRY\_INFO](../Topic/SINK_ENTRY_INFO.md) 매크로.  
  
-   처리에 관심이 메서드를 구현 합니다.  
  
-   싱 및 이벤트 소스를 싱.  
  
## 예제  
 다음 예제에서는 처리 하는 방법을 보여 줍니다 있는  **DocumentChange** 이벤트가 Word에서  **응용 프로그램** 개체.  이 이벤트는 메서드로 정의 되어 있는  **ApplicationEvents** dispinterface를.  
  
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
  
 [!code-cpp[NVC_ATL_EventHandlingSample#1](../atl/codesnippet/CPP/using-idispeventsimpleimpl_1.h)]  
  
 실제로이 예제에서 사용 되는 형식 라이브러리에서 CLSID 단어 됩니다  **응용 프로그램** 개체와의 IID는  **ApplicationEvents** 인터페이스.  이 정보는 컴파일 타임에만 사용 됩니다.  
  
 다음 코드는 simple.h에 나타납니다.  관련 코드 주석으로 표시 됩니다.  
  
 [!code-cpp[NVC_ATL_EventHandlingSample#3](../atl/codesnippet/CPP/using-idispeventsimpleimpl_2.h)]  
  
 다음 코드는 simple.cpp에서입니다.  
  
 [!code-cpp[NVC_ATL_EventHandlingSample#4](../atl/codesnippet/CPP/using-idispeventsimpleimpl_3.cpp)]  
  
## 참고 항목  
 [이벤트 처리](../atl/event-handling-and-atl.md)   
 [ATLEventHandling 샘플](../top/visual-cpp-samples.md)