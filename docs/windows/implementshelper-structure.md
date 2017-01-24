---
title: "ImplementsHelper 구조체 | Microsoft Docs"
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
  - "implements/Microsoft::WRL::Details::ImplementsHelper"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ImplementsHelper 구조체"
ms.assetid: b857ba80-81bd-4e53-92b6-210991954243
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ImplementsHelper 구조체
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL 인프라구조체를 지원하고 코드에서 직접적으로 사용되는 것을 의도하지 않습니다.  
  
## 구문  
  
```  
template <  
   typename RuntimeClassFlagsT,  
   typename ILst,  
   bool IsDelegateToClass  
>  
friend struct Details::ImplementsHelper;  
```  
  
#### 매개 변수  
 `RuntimeClassFlagsT`  
 하나 이상의 [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) 열거자의 지정된 플래그의 필드입니다.  
  
 `ILst`  
 인터페이스 ID의 목록입니다.  
  
 `IsDelegateToClass`  
 구현의 현재 인스턴스가 `ILst` 에서 첫 번째 인터페이스 ID의 기본 클래스이면 `true` 를 지정합니다, 그렇지 않으면 `false`  
  
## 설명  
 [구현](../windows/implements-structure.md) 구초제를 구현하는 것을 돕습니다.  
  
 이 서식 파일 인터페이스 목록을 트래버스 및 기본 클래스 및 QueryInterface를 사용하도록 설정하는 데 필요한 정보를 추가합니다.  
  
## 멤버  
  
## 상속 계층  
 `ImplementsHelper`  
  
## 요구 사항  
 **헤더:** implements.h  
  
 **네임스페이스:** Microsoft::WRL::Details  
  
## 참고 항목  
 [Reference \(Windows Runtime Library\)](http://msdn.microsoft.com/ko-kr/00000000-0000-0000-0000-000000000000)   
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)