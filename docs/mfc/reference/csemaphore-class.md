---
title: "CSemaphore Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CSemaphore"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSemaphore class"
  - "세마포"
  - "synchronization objects, 세마포"
ms.assetid: 385fc7e4-8f86-4be2-85e1-d23b38c12f7f
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CSemaphore Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

개체 클래스의 `CSemaphore` "세마포"를 나타내는, 즉 제한 된 개수의 스레드만 액세스를 유지 관리 하려면 하나 이상의 프로세스에서 현재 지정 된 리소스에 액세스 하는 스레드 수가 허용 하는 동기화 개체인.  
  
## 구문  
  
```  
class CSemaphore : public CSyncObject  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CSemaphore::CSemaphore](../Topic/CSemaphore::CSemaphore.md)|`CSemaphore` 개체를 생성합니다.|  
  
## 설명  
 세마포만 제한 된 수의 사용자를 지원할 수 있는 공유 리소스에 액세스를 제어 하는 데 유용 합니다.  현재 개수는 `CSemaphore` 개체 수는 허용 된 사용자를 추가 합니다.  카운트가 0이 되 면 모든 시도 리소스 제어를 사용 하는  **CSemaphore**  개체 시스템 큐에 삽입 되 고 두 시간 초과 될 때까지 기다려야 또는 카운트가 0 위의 상승.  제어 된 리소스에 액세스할 수 있는 동시 사용자의 최대 수를 생성 하는 동안 지정 된 `CSemaphore` 개체.  
  
 사용 하는  **CSemaphore**  개체, 구성 된 `CSemaphore` 필요할 때 개체.  세마포를 기다려야 합니다 이름을 지정 하 고 응용 프로그램이 처음에 소유 해야 합니다.  생성자는 반환 될 때 다음 세마포를 액세스할 수 있습니다.  호출  [CSyncObject::Unlock](../Topic/CSyncObject::Unlock.md) 완료 되 면 제어 된 리소스에 액세스 합니다.  
  
 사용 하는 또 다른 방법은 `CSemaphore` 개체는 형식의 변수를 추가 하려면 `CSemaphore` 컨트롤에 원하는 클래스를 데이터 멤버로.  제어 개체 생성 시 생성자의 호출을 `CSemaphore` 초기에 지정 된 데이터 멤버 개수, 최대 액세스 횟수, 세마포, \(프로세스 경계에 걸쳐 사용 되는 경우\)의 이름에 액세스 하 고 원하는 보안 특성.  
  
 제어 액세스 리소스 `CSemaphore` 이러한 방법으로 개체 형식의 두 변수를 먼저 만듭니다.  [CSingleLock](../../mfc/reference/csinglelock-class.md) 또는 형식  [CMultiLock](../../mfc/reference/cmultilock-class.md) 리소스를 액세스 멤버 함수에.  다음 잠금 개체가 호출 `Lock` 멤버 함수 \(예를 들어,  [CSingleLock::Lock](../Topic/CSingleLock::Lock.md)\).  이 스레드가 됩니다 중 리소스 액세스, 대기 리소스 해제 및 액세스, 또는 리소스를 해제 하 고 리소스에 액세스 하지 못하는 시간 초과 될 때까지 기다립니다.  스레드로부터 안전한 방식으로 리소스에 액세스 한 경우에.  리소스를 해제 하는 잠금 개체 사용 `Unlock` 멤버 함수 \(예를 들어,  [CSingleLock::Unlock](../Topic/CSingleLock::Unlock.md)\), 또는 허용 범위를 벗어나지 잠금 개체.  
  
 또는 만들 수 있는  **CSemaphore**  독립 개체 및 제어 된 리소스에 액세스 하기 전에 명시적으로 액세스.  이 이렇게 하는 동안에 소스 코드를 읽는 사람이 clearer 오류에 쉽습니다.  
  
 사용 하는 방법에 대 한 자세한 내용은  **CSemaphore**  문서를 참조 하는 개체를  [다중 스레딩: 동기화 클래스 사용 방법](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CSyncObject](../../mfc/reference/csyncobject-class.md)  
  
 `CSemaphore`  
  
## 요구 사항  
 **헤더:**  afxmt.h  
  
## 참고 항목  
 [CSyncObject Class](../../mfc/reference/csyncobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)