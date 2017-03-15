---
title: "ChainInterfaces::Verify 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::ChainInterfaces::Verify"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Verify 메서드"
ms.assetid: c591e130-8686-4130-ba69-1aaedc250038
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# ChainInterfaces::Verify 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

IUnknown 및\/또는 IInspectable로부터 상속받은 `I9` 를 통하여 템플릿 매개변수 `I0` 에 의해 정의된 각각의 인터페이스를 확인합니다. `I9`을 통해, `I0` 은 `I1` 을 상속받습니다.  
  
## 구문  
  
```  
WRL_NOTHROW __forceinline static void Verify();  
```  
  
## 설명  
 확인 작업이 실패 한 경우, `static_assert` 오류를 설명하는 오류 메시지를 내보냅니다.  
  
## 설명  
 템플릿 매개변수 `I0` 및 `I1` 는 필요로 되고, 매개변수 `I2` 은 `I9` 을 통해 선택사항입니다.  
  
## 요구 사항  
 **헤더:** implements.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [ChainInterfaces 구조체](../windows/chaininterfaces-structure.md)