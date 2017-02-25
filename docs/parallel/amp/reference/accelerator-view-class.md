---
title: "accelerator_view 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "amprt/Concurrency::accelerator_view"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "accelerator_view 클래스"
ms.assetid: 9f298c21-bf62-46e0-88b8-01c5c78ef144
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# accelerator_view 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

C\+\+ AMP 데이터 병렬 가속기에서 가상 장치 추상화를 나타냅니다.  
  
## 구문  
  
```  
class accelerator_view;  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[accelerator\_view::accelerator\_view 생성자](../Topic/accelerator_view::accelerator_view%20Constructor.md)|`accelerator_view` 클래스의 새 인스턴스를 초기화합니다.|  
|[accelerator\_view::~accelerator\_view 소멸자](../Topic/accelerator_view::~accelerator_view%20Destructor.md)|`accelerator_view` 개체를 소멸시킵니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[accelerator\_view::create\_marker 메서드](../Topic/accelerator_view::create_marker%20Method.md)|지금까지 이 `accelerator_view` 개체에 전송된 모든 명령의 완료를 추적하는 future를 반환합니다.|  
|[accelerator\_view::flush 메서드](../Topic/accelerator_view::flush%20Method.md)|큐에 대기중인 모든 보류 중인 명령은 `accelerator_view` 개체 실행에 대한 액셀러레이터 키를 전송합니다.|  
|[accelerator\_view::get\_accelerator 메서드](../Topic/accelerator_view::get_accelerator%20Method.md)|`accelerator_view` 개체의 `accelerator` 개체를 반환합니다.|  
|[accelerator\_view::get\_is\_auto\_selection 메서드](../Topic/accelerator_view::get_is_auto_selection%20Method.md)|`accelerator_view` 개체가 [parallel\_for\_each](../Topic/parallel_for_each%20Function%20\(C++%20AMP\).md)로 전달되었을 때 실시간에 적절한 액셀러레이터를 자동으로 선택할지 여부를 나타내는 부울 값을 반환합니다.|  
|[accelerator\_view::get\_is\_debug 메서드](../Topic/accelerator_view::get_is_debug%20Method.md)|`accelerator_view` 개체에 확장 오류 보고를 위해 DEBUG 레이어가 활성화되었는지 여부를 나타내는 부울 값을 반환합니다.|  
|[accelerator\_view::get\_queuing\_mode 메서드](../Topic/accelerator_view::get_queuing_mode%20Method.md)|`accelerator_view` 개체의 queuing 모드를 반환합니다.|  
|[accelerator\_view::get\_version 메서드](../Topic/accelerator_view::get_version%20Method.md)|`accelerator_view`의 버전을 반환합니다.|  
|[accelerator\_view::wait 메서드](../Topic/accelerator_view::wait%20Method.md)|`accelerator_view` 개체에 제출된 모든 명령이 완료될 때까지 대기합니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[accelerator\_view::operator\!\= 연산자](../Topic/accelerator_view::operator!=%20Operator.md)|이 `accelerator_view` 개체를 다른 개체와 비교하여 두 개체가 같으면 `false`를 반환하고, 그렇지 않으면 `true`를 반환합니다.|  
|[accelerator\_view::operator\= 연산자](../Topic/accelerator_view::operator=%20Operator.md)|지정된 `accelerator_view` 개체의 내용을 여기로 복사합니다.|  
|[accelerator\_view::operator\=\= 연산자](../Topic/accelerator_view::operator==%20Operator.md)|이 `accelerator_view` 개체를 다른 개체와 비교하여 두 개체가 같으면 `true`를 반환하고, 그렇지 않으면 `false`를 반환합니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[accelerator\_view::accelerator 데이터 멤버](../Topic/accelerator_view::accelerator%20Data%20Member.md)|`accelerator_view` 개체의 `accelerator` 개체를 가져옵니다.|  
|[accelerator\_view::is\_auto\_selection 데이터 멤버](../Topic/accelerator_view::is_auto_selection%20Data%20Member.md)|`accelerator_view` 개체가 [parallel\_for\_each](../Topic/parallel_for_each%20Function%20\(C++%20AMP\).md)로 전달되었을 때 실시간에 적절한 액셀러레이터를 자동으로 선택할지 여부를 나타내는 부울 값을 가져옵니다.|  
|[accelerator\_view::is\_debug 데이터 멤버](../Topic/accelerator_view::is_debug%20Data%20Member.md)|`accelerator_view` 개체에 확장 오류 보고를 위해 DEBUG 레이어가 활성화되었는지 여부를 나타내는 부울 값을 가져옵니다.|  
|[accelerator\_view::queuing\_mode 데이터 멤버](../Topic/accelerator_view::queuing_mode%20Data%20Member.md)|`accelerator_view` 개체의 큐 모드를 가져옵니다.|  
|[accelerator\_view::version 데이터 멤버](../Topic/accelerator_view::version%20Data%20Member.md)|액셀러레이터 버전을 가져옵니다.|  
  
## 상속 계층  
 `accelerator_view`  
  
## 설명  
 `accelerator_view` 개체는 액셀러레이터 키의 논리적이고 격리된 뷰를 나타냅니다.  하나의 실제 계산 장치에는 논리적이고 격리된 여러 `accelerator_view` 개체가 존재할 수 있습니다.  각 가속기에는 기본 `accelerator_view` 개체가 있습니다.  추가 `accelerator_view` 개체를 만들 수 있습니다.  
  
 물리적 장치는 많은 클라이언트 스레드 간에 공유할 수 있습니다.  클라이언트 스레드는 액셀러레이터의 같은 `accelerator_view` 개체를 협조적으로 사용하거나 각 클라이언트가 다른 클라이언트 스레드와 격리를 위해 독립 `accelerator_view` 개체를 통해 계산 장치와 통신할 수 있습니다.  
  
 `accelerator_view` 개체에는 두 개의 [queuing\_mode 열거형](../../../parallel/amp/reference/queuing-mode-enumeration.md) 상태 중 하나가 있을 수 있습니다.  큐 모드가 `immediate`인 경우 `copy` 및 `parallel_for_each` 같은 명령은 호출자에게 반환되는 즉시 해당 가속기 장치로 보내집니다.  큐 모드가 `deferred`인 경우 이런 명령은 `accelerator_view` 개체에 해당하는 명령 큐에 들어갑니다.  명령은 `flush()`가 호출될 때까지 장치로 실제 전송되지 않습니다.  
  
## 요구 사항  
 **헤더:** amprt.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [Concurrency 네임스페이스\(C\+\+ AMP\)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)