---
title: "CancelTransitionPolicy 열거형 | Microsoft Docs"
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
  - "module/Microsoft::WRL::CancelTransitionPolicy::TransitionFromCanceled"
  - "module/Microsoft::WRL::CancelTransitionPolicy::RemainCanceled"
  - "module/Microsoft::WRL::CancelTransitionPolicy"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CancelTransitionPolicy 열거형"
ms.assetid: 5de49f7d-e5e3-43e9-bbca-666caf226cef
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CancelTransitionPolicy 열거형
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

비동기 작업은 시도의 터미널 상태 전환 방법을 나타냅니다, 완료 또는 오류에 대한 클라이언트 요청이 취소 된 상태로 동작하도록 합니다.  
  
## 구문  
  
```  
enum CancelTransitionPolicy;  
```  
  
## 멤버  
  
### 값  
  
|Name|설명|  
|----------|--------|  
|`RemainCanceled`|비동기 작업이 현재 클라이언트 요청 취소 된 상태이면 전환 터미널 완료 또는 오류 상태와는 달리 취소 된 상태로 유지 됩니다.|  
|`TransitionFromCanceled`|만일 비동기 작업이 현재 클라이언트\-요청에서 취소된 상태일 경우, 완료된 종료 상태 또는 이 플래그를 활용하는 호출에 의해 결정된 오류로서 상태를 취소한 것으로부터 상태가 이행되는 것을 나타냅니다.|  
  
## 요구 사항  
 **헤더:** async.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [Microsoft::WRL 네임스페이스](../windows/microsoft-wrl-namespace.md)