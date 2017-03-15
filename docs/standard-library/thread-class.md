---
title: "thread 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "thread/std::thread"
dev_langs: 
  - "C++"
ms.assetid: df249bc7-ff81-4ff9-a6d6-5e3d9a8f56a1
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# thread 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

확인하는데에 사용되는 개체를 정의하고 응용 프로그램 내의 실행 스레드를 관리합니다.  
  
## 구문  
  
```  
class thread;  
```  
  
## 설명  
 `thread` 개체를 사용하여 관찰하고 응용 프로그램 내의 실행 스레드를 관리합니다.  기본 생성자를 사용하여 생성되는 스레드 개체는 실행 스레드와 연결되지 않습니다.  호출 가능한 개체를 사용하여 생성되는 스레드 개체는 실행의 새 스레드를 만들고 해당 스레드의 호출 가능한 개체를 호출합니다.  스레드 개체는 이동될 수 있지만 복사될 수는 없습니다.  따라서 실행 스레드는 하나의 스레드 개체와만 연결될 수 있습니다.  
  
 모든 스레드 실행은 형식 `thread::id`의 고유 식별자입니다.  함수 `this_thread::get_id` 는 호출 스레드의 식별자를 반환합니다.  멤버 함수 `thread::get_id` 는 스레드 개체에 의해 관리 되는 스레드의 식별자를 반환 합니다.  기본 생성된 스레드 개체에 대하여, `thread::get_id` 메서드는 기본으로 생성된 스레드 개체와 같고 호출 될 때 결합될 수 있는 실행 스레드에 대한 `this_thread::get_id` 에 의해 반환되는 값과 다른 값을 가진 개체를 반환합니다.  
  
## 멤버  
  
### 공용 클래스  
  
|Name|설명|  
|----------|--------|  
|[thread::id 클래스](../Topic/thread::id%20Class.md)|연결된 스레드를 고유하게 식별합니다.|  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[thread::thread 생성자](../Topic/thread::thread%20Constructor.md)|`thread` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[thread::detach 메서드](../Topic/thread::detach%20Method.md)|`thread` 개체로 부터 연결된 스레드를 분리합니다.|  
|[thread::get\_id 메서드](../Topic/thread::get_id%20Method.md)|관련 스레드의 고유 식별자를 반환합니다.|  
|[thread::hardware\_concurrency 메서드](../Topic/thread::hardware_concurrency%20Method.md)|Static.  하드웨어 스레드 컨텍스트 수의 예측을 반환합니다.|  
|[thread::join 메서드](../Topic/thread::join%20Method.md)|관련된 스레드가 완료 될 때까지 차단됩니다.|  
|[thread::joinable 메서드](../Topic/thread::joinable%20Method.md)|관련된 스레드가 참가할 수 있는 여부를 지정합니다.|  
|[thread::native\_handle 메서드](../Topic/thread::native_handle%20Method.md)|스레드 핸들을 나타내는 특정한 구현 형식을 반환합니다.|  
|[thread::swap 메서드](../Topic/thread::swap%20Method.md)|지정된 `thread` 개체와 개체 상태를 바꿉니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[thread::operator\= 연산자](../Topic/thread::operator=%20Operator.md)|현재 스레드 `thread` 개체와 스레드를 연결합니다.|  
  
## 요구 사항  
 **헤더:** thread  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)   
 [\<thread\>](../standard-library/thread.md)