---
title: "combinable 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ppl/concurrency::combinable"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "combinable 클래스"
ms.assetid: fe0bfbf6-6250-47da-b8d0-f75369f0b5be
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 20
---
# combinable 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

`combinable<T>` 개체는 병렬 알고리즘 동안 데이터의 스레드\-전용 복사본을 제공하고 잠금이 없는 스레드\-로컬 하위 계산을 수행하기 위한 것입니다.  병렬 작업이 끝나면 스레드 전용 하위 계산을 최종 결과에 병합할 수 있습니다.  이 클래스는 공유 변수 대신 사용할 수 있으며 해당 공유 변수에 대한 경합이 있는 경우 성능을 개선할 수 있습니다.  
  
## 구문  
  
```  
template<  
   typename _Ty  
>  
class combinable;  
```  
  
#### 매개 변수  
 `_Ty`  
 병합된 최종 결과의 데이터 형식입니다.  형식은 복사 생성자 및 기본 생성자여야 합니다.  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[combinable::combinable 소멸자](../Topic/combinable::combinable%20Constructor.md)|오버로드됨.  새 `combinable` 개체를 생성합니다.|  
|[combinable::~combinable 소멸자](../Topic/combinable::~combinable%20Destructor.md)|`combinable` 개체를 소멸시킵니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[combinable::clear 메서드](../Topic/combinable::clear%20Method.md)|이전 사용에서 중간 계산 결과를 지웁니다.|  
|[combinable::combine 메서드](../Topic/combinable::combine%20Method.md)|제공된 combine 함수를 호출하여 스레드 로컬 하위 계산 집합에서 최종 값을 계산합니다.|  
|[combinable::combine\_each 메서드](../Topic/combinable::combine_each%20Method.md)|스레드 로컬 하위 계산마다 한 번씩 제공된 combine 함수를 호출하여 스레드 로컬 하위 계산 집합에서 최종 값을 계산합니다.  최종 결과는 함수 개체에 의해 누적된 것입니다.|  
|[combinable::local 메서드](../Topic/combinable::local%20Method.md)|오버로드됨.  스레드 전용 하위 계산에 대한 참조를 반환합니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[combinable::operator \= 연산자](../Topic/combinable::operator=%20Operator.md)|다른 `combinable` 개체에서 `combinable` 개체에 할당합니다.|  
  
## 설명  
 자세한 내용은 [병렬 컨테이너 및 개체](../../../parallel/concrt/parallel-containers-and-objects.md)을 참조하십시오.  
  
## 상속 계층  
 `combinable`  
  
## 요구 사항  
 **헤더:** ppl.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [동시성 네임스페이스](../../../parallel/concrt/reference/concurrency-namespace.md)