---
title: "DeferrableEventArgs::GetDeferral 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
ms.assetid: ef6dc7c5-b0be-4b85-8507-d3fd97f2185d
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# DeferrableEventArgs::GetDeferral 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

지연된 이벤트를 나타내는 [Deferral](http://go.microsoft.com/fwlink/?LinkId=526520)\(영문\) 개체에 대한 참조를 가져옵니다.  
  
## 구문  
  
```cpp  
HRESULT GetDeferral([out, retval] Windows::Foundation::IDeferral** result)  
```  
  
#### 매개 변수  
 `result`  
 호출이 완료될 때 [Deferral](http://go.microsoft.com/fwlink/?LinkId=526520)\(영문\) 개체를 참조하는 포인터입니다.  
  
## 반환 값  
 성공하면 S\_OK이고, 그렇지 않으면 오류를 나타내는 HRESULT입니다.  
  
## 설명  
 코드 예제는 [DeferrableEventArgs 클래스](../windows/deferrableeventargs-class.md)를 참조하세요.  
  
## 요구 사항  
 **헤더:** event.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [DeferrableEventArgs 클래스](../windows/deferrableeventargs-class.md)