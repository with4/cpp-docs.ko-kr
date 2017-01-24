---
title: "CCriticalSection Class | Microsoft Docs"
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
  - "CCriticalSection"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CCriticalSection class"
  - "critical sections"
  - "동기화 클래스, CCriticalSection class"
  - "synchronization objects, critical section"
ms.assetid: f776f74b-5b0b-4f32-9c13-2b8e4a0d7b2b
caps.latest.revision: 21
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CCriticalSection Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"임계" 나타냅니다\-스레드씩 코드 섹션 이나 한 리소스에 액세스 하려면 한 번에 하나의 스레드가 있습니다.  
  
## 구문  
  
```  
class CCriticalSection : public CSyncObject  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CCriticalSection::CCriticalSection](../Topic/CCriticalSection::CCriticalSection.md)|`CCriticalSection` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CCriticalSection::Lock](../Topic/CCriticalSection::Lock.md)|사용 하 여 액세스 하는 `CCriticalSection` 개체입니다.|  
|[CCriticalSection::Unlock](../Topic/CCriticalSection::Unlock.md)|릴리스는 `CCriticalSection` 개체입니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[CCriticalSection::operator CRITICAL\_SECTION\*](../Topic/CCriticalSection::operator%20CRITICAL_SECTION*.md)|내부에 대 한 포인터를 검색 합니다.  **CRITICAL\_SECTION** 개체입니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CCriticalSection::m\_sect](../Topic/CCriticalSection::m_sect.md)|A  **CRITICAL\_SECTION** 개체입니다.|  
  
## 설명  
 임계 한 번에 하나의 스레드만 데이터 또는 일부 다른 제어 리소스를 수정할 수 있는 경우에 유용 합니다.  예를 들어, 노드를 연결 된 목록에 추가 한 번에 하나의 스레드에서만 허용 되어야 하는 프로세스입니다.  사용 하는 `CCriticalSection` 연결 된 목록에서 한 번에 하나의 스레드만 목록에 액세스할 수만 제어 하는 개체입니다.  
  
> [!NOTE]
>  기능을 `CCriticalSection` 클래스는 Win32 실제 제공 된  **CRITICAL\_SECTION** 개체.  
  
 중요 섹션 뮤텍스 대신 사용 됩니다 \(참조  [CMutex](../../mfc/reference/cmutex-class.md)\) 속도 중요 시점과 프로세스 경계 간의 리소스 사용 되지 않습니다.  
  
 사용 하는 방법은 두 가지가 `CCriticalSection` 개체: 독립 실행형 및 포함 된 클래스에서입니다.  
  
-   독립 실행형 메서드를 사용 하는 독립 실행형 `CCriticalSection` 개체, 생성 된 `CCriticalSection` 필요할 때 개체.  생성자에서 성공적으로 반환 후에 명시적으로 개체를 잠글  [잠금](../Topic/CCriticalSection::Lock.md).  호출  [잠금 해제](../Topic/CCriticalSection::Unlock.md) 완료 되 면 중요 섹션에 액세스 합니다.  Clearer 소스 코드를 읽는 사람이 하는 동안이 메서드를 임계 전과 후 액세스 잠금을 해제 하는 것 처럼 오류를 더 쉽습니다.  
  
     사용 하는 것이 바람직한 방법 메서드는  [CSingleLock](../../mfc/reference/csinglelock-class.md) 클래스입니다.  도 `Lock` 및 `Unlock` 메서드가 있지만 필요가 예외가 발생 하면 리소스를 잠금 해제에 대 한 걱정 합니다.  
  
-   수 공유할 수도 클래스는 여러 개의 스레드를 추가 하 여 메서드를 포함 한 `CCriticalSection`\-형식 데이터 멤버를 클래스 및 필요한 경우 데이터 멤버를 잠금.  
  
 사용에 대 한 자세한 내용은 `CCriticalSection` 문서를 참조 하는 개체를  [다중 스레딩: 동기화 클래스 사용 방법](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CSyncObject](../../mfc/reference/csyncobject-class.md)  
  
 `CCriticalSection`  
  
## 요구 사항  
 **헤더:**  afxmt.h  
  
## 참고 항목  
 [CSyncObject Class](../../mfc/reference/csyncobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CMutex Class](../../mfc/reference/cmutex-class.md)