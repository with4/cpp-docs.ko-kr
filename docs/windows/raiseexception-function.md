---
title: "RaiseException 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "internal/Microsoft::WRL::Details::RaiseException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RaiseException 함수"
ms.assetid: f9c74f6d-112a-4d2e-900f-622f795d5dbf
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# RaiseException 함수
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL 인프라구조체를 지원하고 코드에서 직접적으로 사용되는 것을 의도하지 않습니다.  
  
## 구문  
  
```  
inline void __declspec(noreturn)  
   RaiseException(  
      HRESULT hr,   
      DWORD dwExceptionFlags = EXCEPTION_NONCONTINUABLE);  
```  
  
#### 매개 변수  
 `hr`  
 예외 코드는 예외 발생. 즉, 실패 한 작업의 HRESULT입니다.  
  
 `dwExceptionFlags`  
 비연속적 예외가 \(플래그 값은 0\), 또는 \(flag 값은 0이 아닌\) noncontinuable 예외를 나타내는 플래그입니다.  기본적으로 예외가 계속할입니다.  
  
## 설명  
 호출 스레드에서 예외가 발생합니다.  
  
 Windows **RaiseException** 함수에 대하여 참조하십시오.  
  
## 요구 사항  
 **헤더:**  internal.h  
  
 **네임스페이스:** Microsoft::WRL::Details  
  
## 참고 항목  
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)