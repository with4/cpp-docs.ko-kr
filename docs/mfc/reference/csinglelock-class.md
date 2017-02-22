---
title: "CSingleLock Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CSingleLock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSingleLock class"
  - "synchronization objects, 액세스 제어"
  - "스레딩[MFC], 액세스 제어"
  - "스레딩[MFC], 동기화"
ms.assetid: 7dae7288-8066-4a3e-85e0-78d28bfc6bc8
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CSingleLock Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

다중 스레드 프로그렘에서 한 리소스에 대한 액세스를 제어할 때 사용하는 액세스 제어 메커니즘을 나타냅니다.  
  
## 구문  
  
```  
  
class CSingleLock  
  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CSingleLock::CSingleLock](../Topic/CSingleLock::CSingleLock.md)|`CSingleLock` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CSingleLock::IsLocked](../Topic/CSingleLock::IsLocked.md)|개체가 잠겨 있는지 여부를 결정 합니다.|  
|[CSingleLock::Lock](../Topic/CSingleLock::Lock.md)|동기화 개체를 기다립니다.|  
|[CSingleLock::Unlock](../Topic/CSingleLock::Unlock.md)|동기화 개체를 해제합니다.|  
  
## 설명  
 `CSingleLock`기본 클래스에 없는 것입니다.  
  
 동기화 클래스를 사용 하려면  [CSemaphore](../../mfc/reference/csemaphore-class.md),  [CMutex](../../mfc/reference/cmutex-class.md),  [아니오](../../mfc/reference/ccriticalsection-class.md), 및  [CEvent](../../mfc/reference/cevent-class.md), 하나 만들어야는 `CSingleLock` 또는  [CMultiLock](../../mfc/reference/cmultilock-class.md) 개체를 동기화 개체를 해제 하 고 대기 합니다.  사용 `CSingleLock` 만 해야 한 번에 하나의 개체에서 대기 하는 경우.  사용  **CMultiLock**  때 특정 시간에 사용할 수 있는 여러 개체입니다.  
  
 사용 하는 `CSingleLock` 개체, 제어 된 리소스 클래스에 멤버 함수 내 해당 생성자를 호출 합니다.  다음 호출에서  [IsLocked](../Topic/CSingleLock::IsLocked.md) 멤버 함수는 리소스를 사용할 수 있는지 확인 합니다.  이 경우 나머지 멤버 함수를 계속 합니다.  리소스를 사용할 수 없는 경우, 출시 되는 리소스에 지정 된 시간 대기 또는 실패를 반환 합니다.  리소스 사용이 완료 된 후 호출 하는  [잠금 해제](../Topic/CSingleLock::Unlock.md) 작동 하는 경우는 `CSingleLock` 개체는 다시 사용 하거나의 `CSingleLock` 개체 소멸.  
  
 `CSingleLock`개체에서 파생 되는 개체의 필요  [CSyncObject](../../mfc/reference/csyncobject-class.md).  이 일반적으로 제어 하는 리소스의 클래스의 데이터 멤버입니다.  사용 하는 방법에 대 한 자세한 내용은 `CSingleLock` 문서를 참조 하는 개체를  [다중 스레딩: 동기화 클래스 사용 방법](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).  
  
## 상속 계층 구조  
 `CSingleLock`  
  
## 요구 사항  
 **헤더:**  afxmt.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CMultiLock Class](../../mfc/reference/cmultilock-class.md)