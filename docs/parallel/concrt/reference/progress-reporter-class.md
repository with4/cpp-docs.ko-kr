---
title: "progress_reporter 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ppltasks/concurrency::progress_reporter"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "progress_reporter 클래스"
ms.assetid: b836efab-2d05-4649-b6fa-d15236f1f813
caps.latest.revision: 11
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# progress_reporter 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

진행률 보고자 클래스를 사용하면 특정 형식의 진행률 알림을 사용할 수 있습니다.  각 progress\_reporter 개체는 특정 비동기 작업 또는 작업에 바인딩됩니다.  
  
## 구문  
  
```  
template<  
   typename _ProgressType  
>  
class progress_reporter;  
```  
  
#### 매개 변수  
 `_ProgressType`  
 진행률 보고자를 통해 보고되는 각 진행률 알림의 페이로드 형식입니다.  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[progress\_reporter::progress\_reporter 생성자](../Topic/progress_reporter::progress_reporter%20Constructor.md)||  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[progress\_reporter::report 메서드](../Topic/progress_reporter::report%20Method.md)|진행률 보고서를 이 진행률 보고자가 바인딩된 비동기 작업으로 보냅니다.|  
  
## 설명  
 이 형식은 Windows 스토어 응용 프로그램에만 사용할 수 있습니다.  
  
## 상속 계층  
 `progress_reporter`  
  
## 요구 사항  
 **헤더:** ppltasks.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [동시성 네임스페이스](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [create\_async 함수](../Topic/create_async%20Function.md)