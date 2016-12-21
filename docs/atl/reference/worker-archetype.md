---
title: "Worker Archetype | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Worker archetype"
ms.assetid: 834145cd-09d3-4149-bc99-620e1871cbfb
caps.latest.revision: 16
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Worker Archetype
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

준수 하는 클래스는  *작업자* 전형 제공 코드 프로세스 작업 항목을 스레드 풀에 대기 합니다.  
  
 **구현**  
  
 이 전형에 맞는 클래스를 구현 하려면 클래스는 다음과 같은 기능을 제공 해야 합니다.  
  
|메서드|설명|  
|---------|--------|  
|[초기화](../Topic/WorkerArchetype::Initialize.md)|모든 요청을 전달 하기 전에 작업자 개체를 초기화 하기 위해 호출  [실행](../Topic/WorkerArchetype::Execute.md).|  
|[Execute](../Topic/WorkerArchetype::Execute.md)|작업 항목을 처리 하기 위해 호출 됩니다.|  
|[종료](../Topic/WorkerArchetype::Terminate.md)|모든 요청에 전달 된 후 작업자 개체 초기화를 호출  [실행](../Topic/WorkerArchetype::Execute.md).|  
  
|형식 정의|설명|  
|-----------|--------|  
|[RequestType](../Topic/WorkerArchetype::RequestType.md)|작업자 클래스에서 처리할 수 있는 작업 항목의 형식에 대 한 형식 정의입니다.|  
  
 일반적인  *작업자* 클래스를 다음과 같이 찾습니다:  
  
 [!code-cpp[NVC_ATL_Utilities#137](../../atl/codesnippet/CPP/worker-archetype_1.cpp)]  
  
 **기존 구현**  
  
 이러한 클래스는이 전형에 준수.  
  
|클래스|설명|  
|---------|--------|  
|[CNonStatelessWorker](../../atl/reference/cnonstatelessworker-class.md)|스레드 풀에서 요청을 받아이 만들어지고 각 요청에 대 한 파괴 하는 작업자 개체에 전달 합니다.|  
  
 **사용할 도구**  
  
 이 전형에 맞게 클래스 템플릿 매개 변수를 예상:  
  
|매개 변수 이름|다음 리소스에서 사용|  
|--------------|-----------------|  
|*작업자*|[CThreadPool](../../atl/reference/cthreadpool-class.md)|  
|*작업자*|[CNonStatelessWorker](../../atl/reference/cnonstatelessworker-class.md)|  
  
## 요구 사항  
 **헤더:** atlutil.h  
  
## 참고 항목  
 [Archetypes](../../atl/reference/atl-archetypes.md)   
 [개념](../../atl/active-template-library-atl-concepts.md)   
 [ATL COM Desktop Components](../../atl/atl-com-desktop-components.md)