---
title: "InvokeHelper::Invoke 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "event/Microsoft::WRL::Details::InvokeHelper::Invoke"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Invoke 메서드"
ms.assetid: 98618815-c30e-4699-b3dd-203c91b1bf3b
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# InvokeHelper::Invoke 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL 인프라구조체를 지원하고 코드에서 직접적으로 사용되는 것을 의도하지 않습니다.  
  
## 구문  
  
```  
STDMETHOD(  
   Invoke  
)();  
STDMETHOD(  
   Invoke  
)(typename Traits;  
STDMETHOD(  
   Invoke  
)( typename Traits;  
STDMETHOD(  
   Invoke  
)( typename Traits;  
STDMETHOD(  
   Invoke  
)( typename Traits;  
STDMETHOD(  
   Invoke  
)( typename Traits;  
STDMETHOD(  
   Invoke  
)( typename Traits;  
STDMETHOD(  
   Invoke  
)( typename Traits;  
STDMETHOD(  
   Invoke  
)( typename Traits;  
STDMETHOD(  
   Invoke  
)( typename Traits;  
```  
  
#### 매개 변수  
 `arg1`  
 인수 1입니다.  
  
 `arg2`  
 인수 2입니다.  
  
 `arg3`  
 인수 3입니다.  
  
 `arg4`  
 인수 4입니다.  
  
 `arg5`  
 인수 5입니다.  
  
 `arg6`  
 인수 6입니다.  
  
 `arg7`  
 인수 7입니다.  
  
 `arg8`  
 인수 8입니다.  
  
 `arg9`  
 인수 9입니다.  
  
## 반환 값  
 성공 하면 S\_OK 그렇지 않으면 오류를 암시하는 HRESULT입니다.  
  
## 설명  
 지정한 개수의 인수를 포함하는 시그니처를 가진 이벤트 처리기를 호출 합니다.  
  
## 요구 사항  
 **헤더:** event.h  
  
 **네임스페이스:** Microsoft::WRL::Details  
  
## 참고 항목  
 [InvokeHelper 구조체](../windows/invokehelper-structure.md)   
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)