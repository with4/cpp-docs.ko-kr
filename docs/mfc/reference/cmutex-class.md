---
title: "CMutex Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "Mutex"
  - "CMutex"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMutex class"
  - "mutex"
  - "동기화 클래스, CMutex class"
  - "synchronization objects, mutex"
ms.assetid: 6330c050-4f01-4195-a099-2029b92f8cf1
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CMutex Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"뮤텍스"를 나타내는\-스레드 상호 배타적으로 액세스 하는 리소스를 사용할 수 있는 동기화 개체입니다.  
  
## 구문  
  
```  
class CMutex : public CSyncObject  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CMutex::CMutex](../Topic/CMutex::CMutex.md)|`CMutex` 개체를 생성합니다.|  
  
## 설명  
 뮤텍스는 한 번에 하나의 스레드만 데이터 또는 일부 다른 제어 리소스를 수정할 수 있는 경우에 유용 합니다.  예를 들어, 노드를 연결 된 목록에 추가 한 번에 하나의 스레드에서만 허용 되어야 하는 프로세스입니다.  사용 하는 `CMutex` 연결 된 목록에서 한 번에 하나의 스레드만 목록에 액세스할 수만 제어 하는 개체입니다.  
  
 사용 하는 `CMutex` 개체, 구성 된 `CMutex` 필요할 때 개체.  뮤텍스를 대기 하려는 이름을 지정 하 고 응용 프로그램이 처음에 소유 해야 합니다.  그런 다음 생성자는 반환 될 때 뮤텍스를 액세스할 수 있습니다.  호출  [CSyncObject::Unlock](../Topic/CSyncObject::Unlock.md) 완료 되 면 제어 된 리소스에 액세스 합니다.  
  
 사용 하는 또 다른 방법은 `CMutex` 개체는 형식의 변수를 추가 하려면 `CMutex` 컨트롤에 원하는 클래스를 데이터 멤버로.  제어 개체 생성 시 생성자의 호출을 `CMutex` 뮤텍스 처음 소유 하지, 뮤텍스 \(프로세스 경계에 걸쳐 사용 되는 경우\), 이름 및 보안 특성을 원하는 경우 지정 된 데이터 멤버입니다.  
  
 제어 액세스 리소스 `CMutex` 이러한 방법으로 개체 형식의 두 변수를 먼저 만듭니다.  [CSingleLock](../../mfc/reference/csinglelock-class.md) 또는 형식  [CMultiLock](../../mfc/reference/cmultilock-class.md) 리소스를 액세스 멤버 함수에.  다음 잠금 개체가 호출 `Lock` 멤버 함수 \(예를 들어,  [CSingleLock::Lock](../Topic/CSingleLock::Lock.md)\).  이 스레드가 됩니다 중 리소스 액세스, 대기 리소스 해제 및 액세스, 또는 리소스를 해제 하 고 리소스에 액세스 하지 못하는 시간 초과 될 때까지 기다립니다.  스레드로부터 안전한 방식으로 리소스에 액세스 한 경우에.  리소스를 해제 하는 잠금 개체 사용 `Unlock` 멤버 함수 \(예를 들어,  [CSingleLock::Unlock](../Topic/CSingleLock::Unlock.md)\), 또는 허용 범위를 벗어나지 잠금 개체.  
  
 사용에 대 한 자세한 내용은 `CMutex` 문서를 참조 하는 개체를  [다중 스레딩: 동기화 클래스 사용 방법](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CSyncObject](../../mfc/reference/csyncobject-class.md)  
  
 `CMutex`  
  
## 요구 사항  
 **헤더:**  afxmt.h  
  
## 참고 항목  
 [CSyncObject Class](../../mfc/reference/csyncobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)