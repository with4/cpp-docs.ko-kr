---
title: "CloakedIid 구조체 | Microsoft Docs"
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
  - "implements/Microsoft::WRL::CloakedIid"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CloakedIid 구조체"
ms.assetid: 82e0e377-ca3a-46bc-b850-ae2c46c15bb5
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CloakedIid 구조체
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

지정된 인터페이스는 IID 목록에 액세스할 수 없습니다 RuntimeClass, 구현 및 ChainInterfaces 서식 파일을 나타냅니다.  
  
## 구문  
  
```  
template<  
   typename T  
>  
struct CloakedIid : T;  
```  
  
#### 매개 변수  
 `T`  
 인터페이스는 숨겨진 \(숨겨진\)입니다.  
  
## 설명  
 다음은 CloakedIid를 사용하는 방법의 예: `struct MyRuntimeClass : RuntimeClass<CloakedIid<IMyCloakedInterface>> {}`.  
  
## 상속 계층  
 `T`  
  
 `CloakedIid`  
  
## 요구 사항  
 **헤더:** implements.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [Microsoft::WRL 네임스페이스](../windows/microsoft-wrl-namespace.md)