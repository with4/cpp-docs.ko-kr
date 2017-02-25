---
title: "CEvent Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CEvent"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CEvent class"
  - "동기화 클래스, CEvent class"
  - "synchronization objects, event"
ms.assetid: df676042-ce27-4702-800a-e73ff4f44395
caps.latest.revision: 27
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 29
---
# CEvent Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

한 스레드가 다른 스레드에게 이벤트가 발생 했음을 알리기 위해 사용 하는 동기화 개체인 이벤트를 나타냅니다.  
  
## 구문  
  
```  
class CEvent : public CSyncObject  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CEvent::CEvent](../Topic/CEvent::CEvent.md)|`CEvent` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CEvent::PulseEvent](../Topic/CEvent::PulseEvent.md)|설정 이벤트를 사용 가능 \(신호\)를 대기 스레드를 해제 하 고 이벤트를 사용할 수 없게 합니다 \(nonsignaled\) 설정.|  
|[CEvent::ResetEvent](../Topic/CEvent::ResetEvent.md)|이벤트에 사용할 수 없습니다 \(nonsignaled\) 설정합니다.|  
|[CEvent::SetEvent](../Topic/CEvent::SetEvent.md)|이벤트에 사용할 수 있는 \(신호\) 설정 하 고 모든 대기 스레드를 해제 합니다.|  
|[CEvent::Unlock](../Topic/CEvent::Unlock.md)|이벤트 개체를 해제합니다.|  
  
## 설명  
 이벤트 스레드는 해당 작업을 수행 하는 경우 알아야 할 때 유용 합니다.  예를 들어, 스레드가 데이터를 데이터 보관 저장소에 복사 하는 새 데이터를 사용할 수 있을 때 알림을 받아야 합니다.  사용 하는 `CEvent` 개체에서 새 데이터를 사용할 때 복사 스레드를 알리기 위해 스레드가 해당 작업을 빨리 수행할 수 있습니다.  
  
 `CEvent`개체 유형에 있습니다: 수동 및 자동.  
  
 자동 `CEvent` 개체를 자동으로 반환 아닌 신호 \(사용할 수 없음\) 상태에 적어도 하나의 스레드를 해제 한 후.  기본적으로 `CEvent` 개체인 자동 전달 하지 않으면 `TRUE` 에 있는 `bManualReset` 매개 변수가 생성 되는 동안.  
  
 수동 `CEvent` 개체를 유지 하는 상태로 설정 하  [SetEvent](../Topic/CEvent::SetEvent.md) 또는  [ResetEvent](../Topic/CEvent::ResetEvent.md) 다른 함수를 호출할 때까지.  수동으로 만들려면 `CEvent` 개체, 전달 `TRUE` 에 있는 `bManualReset` 매개 변수가 생성 되는 동안.  
  
 사용 하는 `CEvent` 개체, 구성 된 `CEvent` 필요할 때 개체.  대기 신청이 처음이 소유 해야 하는 지정 하려는 이벤트의 이름을 지정 합니다.  그런 다음 생성자는 반환 될 때 이벤트를 액세스할 수 있습니다.  호출  [SetEvent](../Topic/CEvent::SetEvent.md) 신호 \(오프\) 이벤트 개체 및 다음 호출  [잠금 해제](../Topic/CEvent::Unlock.md) 완료 되 면 제어 된 리소스에 액세스 합니다.  
  
 사용 하는 또 다른 방법은 `CEvent` 개체는 형식의 변수를 추가 하려면 `CEvent` 컨트롤에 클래스를 데이터 멤버로.  제어 개체 생성 시 생성자의 호출을 `CEvent` 데이터 멤버 여부 이벤트가 처음 신호, 및 specifythe 형식의 원하는 이벤트 개체 \(프로세스 경계에 걸쳐 사용 되는 경우\)에 이벤트의 이름 지정 하 고 모든 보안 특성을.  
  
 제어 된 리소스에 액세스 하는 `CEvent` 개체를이 이런 식으로, 처음 두 형식의 변수를 만들  [CSingleLock](../../mfc/reference/csinglelock-class.md) 또는 형식  [CMultiLock](../../mfc/reference/cmultilock-class.md) 리소스 액세스 방법에서.  다음 호출에서 `Lock` 잠금 개체의 메서드 \(예를 들어,  [CMultiLock::Lock](../Topic/CMultiLock::Lock.md)\).  이 스레드가 됩니다 중 리소스, 출시 하 고 액세스, 리소스 해제 대기 리소스에 대 한 대기 시간 초과 대 한 액세스 및 리소스에 액세스할 수 없습니다.  스레드로부터 안전한 방식으로 리소스에 액세스 한 경우에.  리소스를 해제 하려면 호출 `SetEvent` 이벤트 개체를 신호 하 고 사용 하는 `Unlock` 잠금 개체의 메서드 \(예를 들어,  [CMultiLock::Unlock](../Topic/CMultiLock::Unlock.md)\), 또는 잠금 개체가 범위를 벗어난 수 있습니다.  
  
 사용 하는 방법에 대 한 자세한 내용은 `CEvent` 개체를 참조 하십시오. [다중 스레딩: 동기화 클래스 사용 방법](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).  
  
## 예제  
 [!code-cpp[NVC_MFC_Utilities#45](../../mfc/codesnippet/CPP/cevent-class_1.cpp)]  
  
 [!code-cpp[NVC_MFC_Utilities#46](../../mfc/codesnippet/CPP/cevent-class_2.cpp)]  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CSyncObject](../../mfc/reference/csyncobject-class.md)  
  
 `CEvent`  
  
## 요구 사항  
 **헤더:**  afxmt.h  
  
## 참고 항목  
 [CSyncObject Class](../../mfc/reference/csyncobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)