---
title: "WeakReference::Resolve 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::Details::WeakReference::Resolve"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Resolve 메서드"
ms.assetid: fc65a4b7-48a0-4d64-a793-37f566fdd8e7
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# WeakReference::Resolve 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL 인프라구조체를 지원하고 코드에서 직접적으로 사용되는 것을 의도하지 않습니다.  
  
## 구문  
  
```  
  
STDMETHOD(Resolve)  
   (REFIID riid,   
   _Deref_out_opt_ IInspectable **ppvObject  
);  
```  
  
#### 매개 변수  
 `riid`  
 인터페이스 ID  
  
 `ppvObject`  
 이 작업을 완료 시, 강력한 참조 횟수가 0이 아닌 경우 현재 강력한 참조의 복사본입니다.  
  
## 반환 값  
  
-   이 작업이 성공 하면 S\_OK, 및 강력한 참조 횟수는 0입니다.  `ppvObject` 매개 변수가 `nullptr`로 설정된 경우  
  
-   이 작업이 성공 하면 S\_OK, 및 강력한 참조 횟수는 0이 아닙니다.  `ppvObject` 매개변수는 강한 참조를 설정 합니다.  
  
-   그렇지 않으면, 이유를 나타내는 이 작업은 실패합니다.  
  
## 설명  
 강한 참조 횟수가 0이 아니면 고정 참조가 현재 값으로 지정된 된 포인터를 설정 합니다.  
  
## 요구 사항  
 **헤더:** implements.h  
  
 **네임스페이스**Microsoft::WRL::Details  
  
## 참고 항목  
 [WeakReference 클래스](../windows/weakreference-class1.md)   
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)