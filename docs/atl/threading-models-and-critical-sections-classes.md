---
title: "Threading Models and Critical Sections Classes | Microsoft Docs"
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
  - "vc.atl.threads.models"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL, critical sections"
  - "ATL, 다중 스레딩"
  - "critical sections"
  - "스레딩[ATL], 모델"
ms.assetid: 759f05ef-6285-4be6-a2cc-78572dd75146
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Threading Models and Critical Sections Classes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

스레딩에 다음 클래스 정의 모델 및 중요 섹션:  
  
-   [CAtlAutoThreadModule](../atl/reference/catlautothreadmodule-class.md) 아파트 모델 스레드 풀링, COM 서버를 구현 합니다.  
  
-   [CAtlAutoThreadModuleT](../atl/reference/catlautothreadmodulet-class.md) 아파트 모델 스레드 풀링, COM 서버를 구현 하는 메서드를 제공 합니다.  
  
-   [CComMultiThreadModel](../atl/reference/ccommultithreadmodel-class.md) 변수 증가 및 감소 스레드로부터 안전한 메서드를 제공 합니다.  임계 영역을 제공합니다.  
  
-   [CComMultiThreadModelNoCS](../atl/reference/ccommultithreadmodelnocs-class.md) 변수 증가 및 감소 스레드로부터 안전한 메서드를 제공 합니다.  임계 영역을 제공 하지 않습니다.  
  
-   [CComSingleThreadModel](../atl/reference/ccomsinglethreadmodel-class.md) 변수 증가 및 감소에 대 한 메서드를 제공 합니다.  임계 영역을 제공 하지 않습니다.  
  
-   [CComObjectThreadModel](../Topic/CComObjectThreadModel.md) 는 단일 개체 클래스에 대 한 적절 한 스레딩 모델 클래스를 결정 합니다.  
  
-   [CComGlobalsThreadModel](../Topic/CComGlobalsThreadModel.md) 전역적으로 사용할 수 있는 개체에 대 한 적절 한 스레딩 모델 클래스를 결정 합니다.  
  
-   [CComAutoCriticalSection](../atl/reference/ccomautocriticalsection-class.md) 획득 및 중요 섹션을 해제 하는 방법에 대 한 메서드가 포함 되어 있습니다.  임계 영역으로 자동으로 초기화 됩니다.  
  
-   [CComCriticalSection](../atl/reference/ccomcriticalsection-class.md) 획득 및 중요 섹션을 해제 하는 방법에 대 한 메서드가 포함 되어 있습니다.  중요 섹션을 명시적으로 초기화 되어야 합니다.  
  
-   [CComFakeCriticalSection](../atl/reference/ccomfakecriticalsection-class.md) 방법에 반영 `CComCriticalSection` 임계 영역을 제공 하지 않고 있습니다.  방법으로 `CComFakeCriticalSection` 아무 작업도 하지 않습니다.  
  
-   [CRTThreadTraits](../atl/reference/crtthreadtraits-class.md) CRT 스레드에 대 한 생성 함수를 제공 합니다.  스레드 CRT 함수를 사용 하려는 경우이 클래스를 사용 합니다.  
  
-   [Win32ThreadTraits](../atl/reference/win32threadtraits-class.md) Windows 스레드를 만드는 함수를 제공 합니다.  스레드 CRT 함수를 사용 하지 않는 경우이 클래스를 사용 합니다.  
  
## 참고 항목  
 [Class Overview](../atl/atl-class-overview.md)