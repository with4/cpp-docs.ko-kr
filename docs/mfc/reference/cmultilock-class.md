---
title: "CMultiLock Class | Microsoft Docs"
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
  - "CMultiLock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMultiLock class"
  - "synchronization objects, 액세스 제어"
ms.assetid: c5b7c78b-1f81-4387-b7dd-2c813c5b6b61
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMultiLock Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

다중 스레드 프로그램에 대한 액세스를 제어할 때 사용하는 액세스 제어 메커니즘을 나타냅니다.  
  
## 구문  
  
```  
class CMultiLock  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CMultiLock::CMultiLock](../Topic/CMultiLock::CMultiLock.md)|`CMultiLock` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMultiLock::IsLocked](../Topic/CMultiLock::IsLocked.md)|배열에 있는 특정 동기화 개체가 잠겨 있는지 여부를 결정 합니다.|  
|[CMultiLock::Lock](../Topic/CMultiLock::Lock.md)|동기화 개체의 배열에서 기다립니다.|  
|[CMultiLock::Unlock](../Topic/CMultiLock::Unlock.md)|소유 하는 동기화 개체를 해제합니다.|  
  
## 설명  
 `CMultiLock`기본 클래스에 없는 것입니다.  
  
 동기화 클래스 사용  [CSemaphore](../../mfc/reference/csemaphore-class.md),  [CMutex](../../mfc/reference/cmutex-class.md), 및  [CEvent](../../mfc/reference/cevent-class.md), 하나를 만들 수 있습니다는  **CMultiLock**  또는  [CSingleLock](../../mfc/reference/csinglelock-class.md) 개체를 동기화 개체를 해제 하 고 대기.  사용  **CMultiLock**  때 특정 시간에 사용할 수 있는 여러 개체입니다.  사용 `CSingleLock` 만 해야 한 번에 하나의 개체에서 대기 하는 경우.  
  
 사용 하는  **CMultiLock**  개체, 배열 하 여 대기할 동기화 개체를 먼저 만듭니다.  그런 다음 호출에서  **CMultiLock**  개체의 생성자 내에서 제어 하는 리소스의 클래스 멤버 함수.  다음 호출에서  [잠금](../Topic/CMultiLock::Lock.md) 리소스를 사용할 수 있는지 확인 하는 멤버 함수 \(신호\).  하나 있으면 나머지 멤버 함수를 계속 합니다.  리소스를 사용할 수 있으면 출시 되는 리소스에 지정 된 시간 대기 또는 실패를 반환 합니다.  자원의 사용이 완료 된 후 호출 하는  [잠금 해제](../Topic/CMultiLock::Unlock.md) 작동 하는 경우는  **CMultiLock**  개체는 다시 사용 하거나의  **CMultiLock**  개체 소멸.  
  
 **CMultiLock**  개체는 가장 유용 많은 수의 스레드가 있는 경우 `CEvent` 개체에 응답 수 있습니다.  모두 포함 하는 배열을 만들는 `CEvent` 포인터를 호출 하 고 `Lock`.  그러면 이벤트 중 하나가 신호를 기다릴 수 있습니다.  
  
 사용 하는 방법에 대 한 자세한 내용은  **CMultiLock**  문서를 참조 하는 개체를  [다중 스레딩: 동기화 클래스 사용 방법](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).  
  
## 상속 계층 구조  
 `CMultiLock`  
  
## 요구 사항  
 **헤더:**  afxmt.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)