---
title: "CNoWorkerThread Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CNoWorkerThread"
  - "ATL.CNoWorkerThread"
  - "CNoWorkerThread"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CNoWorkerThread class"
ms.assetid: 29f06bae-b658-4aac-9c14-331e996d25d1
caps.latest.revision: 21
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CNoWorkerThread Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스에 대 한 인수로 사용 된 `MonitorClass` 동적 캐시를 유지 관리 하지 않을 경우 캐시 클래스 템플릿 매개 변수.  
  
> [!IMPORTANT]
>  런타임에서 Windows를 실행 하는 응용 프로그램에서이 클래스와 해당 멤버를 사용할 수 없습니다.  
  
## 구문  
  
```  
  
class CNoWorkerThread  
  
```  
  
## Members  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[CNoWorkerThread::AddHandle](../Topic/CNoWorkerThread::AddHandle.md)|해당 작동 하는  [CWorkerThread::AddHandle](../Topic/CWorkerThread::AddHandle.md).|  
|[CNoWorkerThread::AddTimer](../Topic/CNoWorkerThread::AddTimer.md)|해당 작동 하는  [CWorkerThread::AddTimer](../Topic/CWorkerThread::AddTimer.md).|  
|[CNoWorkerThread::GetThreadHandle](../Topic/CNoWorkerThread::GetThreadHandle.md)|해당 작동 하는  [CWorkerThread::GetThreadHandle](../Topic/CWorkerThread::GetThreadHandle.md).|  
|[CNoWorkerThread::GetThreadId](../Topic/CNoWorkerThread::GetThreadId.md)|해당 작동 하는  [CWorkerThread::GetThreadId](../Topic/CWorkerThread::GetThreadId.md).|  
|[CNoWorkerThread::Initialize](../Topic/CNoWorkerThread::Initialize.md)|해당 작동 하는  [CWorkerThread::Initialize](../Topic/CWorkerThread::Initialize.md).|  
|[CNoWorkerThread::RemoveHandle](../Topic/CNoWorkerThread::RemoveHandle.md)|해당 작동 하는  [CWorkerThread::RemoveHandle](../Topic/CWorkerThread::RemoveHandle.md).|  
|[CNoWorkerThread::Shutdown](../Topic/CNoWorkerThread::Shutdown.md)|해당 작동 하는  [CWorkerThread::Shutdown](../Topic/CWorkerThread::Shutdown.md).|  
  
## 설명  
 이 클래스는 공용 인터페이스로 제공  [CWorkerThread](../../atl/reference/cworkerthread-class.md).  이 인터페이스 제공 될 것으로 예상 되는 `MonitorClass` 캐시 클래스 템플릿 매개 변수.  
  
 이 클래스의 메서드는 아무 작업도 하지 않으려면 구현 됩니다.  항상 HRESULT를 반환 하는 메서드는 S\_OK를 반환 하 고 0 항상 핸들이 나 스레드 ID를 반환 하는 메서드를 반환 합니다.  
  
## 요구 사항  
 **헤더:** atlutil.h