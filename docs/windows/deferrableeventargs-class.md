---
title: "DeferrableEventArgs 클래스 | Microsoft Docs"
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
ms.assetid: ece89267-7b72-40e1-8185-550c865b070a
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# DeferrableEventArgs 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

지연에 대한 이벤트 인수 형식에 사용되는 템플릿 클래스입니다.  
  
## 구문  
  
```cpp  
template <  
typename TEventArgsInterface,  
typename TEventArgsClass  
>  
class DeferrableEventArgs : public TEventArgsInterface  
  
```  
  
#### 매개 변수  
 `TEventArgsInterface`  
 지연된 이벤트에 대한 인수를 선언하는 인터페이스 형식입니다.  
  
 `TEventArgsClass`  
 `TEventArgsInterface`를 구현하는 클래스입니다.  
  
## 멤버  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[DeferrableEventArgs::GetDeferral 메서드](../windows/deferrableeventargs-getdeferral-method.md)|지연된 이벤트를 나타내는 [Deferral](http://go.microsoft.com/fwlink/?LinkId=526520)\(영문\) 개체에 대한 참조를 가져옵니다.|  
|[DeferrableEventArgs::InvokeAllFinished 메서드](../windows/deferrableeventargs-invokeallfinished-method.md)|지연된 이벤트를 처리하는 모든 처리가 완료되었음을 나타내기 위해 호출됩니다.|  
  
## 설명  
 이 클래스의 인스턴스는 지연된 이벤트에 대한 이벤트 처리기에 전달됩니다.  템플릿 매개 변수는 특정 형식의 지연된 이벤트에 대한 이벤트 인수 세부 정보를 정의하는 인터페이스 및 해당 인터페이스를 구현하는 클래스를 나타냅니다.  
  
 클래스는 지연된 이벤트에 대한 이벤트 처리기에 첫 번째 인수로 표시됩니다.  [GetDeferral](../windows/deferrableeventargs-getdeferral-method.md) 메서드를 호출하여 지연된 이벤트에 대한 모든 정보를 가져올 수 있는 [Deferral](http://go.microsoft.com/fwlink/?LinkId=526520) 개체를 얻을 수 있습니다.  이벤트 처리를 완료한 후 Deferral 개체에 대해 Complete를 호출해야 합니다.  그럼 다음 이벤트 처리기 메서드가 끝날 때 [InvokeAllFinished](../windows/deferrableeventargs-invokeallfinished-method.md)를 호출하여 지연된 모든 이벤트의 완료가 제대로 전달되도록 해야 합니다.  
  
## 요구 사항  
 **헤더:** event.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [Microsoft::WRL 네임스페이스](../windows/microsoft-wrl-namespace.md)