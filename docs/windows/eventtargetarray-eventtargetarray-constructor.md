---
title: "EventTargetArray::EventTargetArray 생성자 | Microsoft Docs"
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
  - "event/Microsoft::WRL::Details::EventTargetArray::EventTargetArray"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "EventTargetArray, 생성자"
ms.assetid: 6c6d3737-3cd3-4515-a8f6-d27901bb8ed2
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# EventTargetArray::EventTargetArray 생성자
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
## 구문  
  
```  
EventTargetArray(  
   _Out_ HRESULT* hr,  
   size_t items  
);  
```  
  
#### 매개 변수  
 `hr`  
 이 생성자 작업을 수행한 후 매개 변수 `hr` 배열 할당 성공 여부를 나타냅니다.  다음 표에서는 가능한 `hr` 에 대한 값을 보여 줍니다.  
  
 S\_OK  
 작업을 성공적으로 완료했습니다.  
  
 E\_OUTOFMEMORY  
 배열에 메모리가 할당되지 않습니다.  
  
 S\_FALSE  
 매개변수 `items` 보다 적거나 또는 0과 같을 경우입니다.  
  
 `items`  
 할당할 복사할 배열 요소 수입니다.  
  
## 설명  
 EventTargetArray 클래스의 새 인스턴스를 초기화합니다.  
  
 EventTargetArray는 EventSource 개체에 이벤트 처리기의 배열을 유지하는 데 사용됩니다.  
  
## 요구 사항  
 **헤더:** event.h  
  
 **네임스페이스**Microsoft::WRL::Details  
  
## 참고 항목  
 [EventTargetArray 클래스](../windows/eventtargetarray-class.md)   
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)