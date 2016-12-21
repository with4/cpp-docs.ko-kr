---
title: "VerifyInterfaceHelper 구조체 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::Details::VerifyInterfaceHelper"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VerifyInterfaceHelper 구조체"
ms.assetid: ea95b641-199a-4fdf-964b-186b40cb3ba7
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# VerifyInterfaceHelper 구조체
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[cppwrl](../windows/includes/cppwrl_md.md)] 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
## 구문  
  
```  
template <  
   bool isWinRTInterface,  
   typename I  
>  
struct VerifyInterfaceHelper;  
  
template <  
   typename I  
>  
struct VerifyInterfaceHelper<false, I>;  
```  
  
#### 매개 변수  
 `I`  
 확인하기 위한 인터페이스  
  
 `isWinRTInterface`  
  
## 설명  
 템플릿 매개 변수로 지정된 인터페이스에 특정 요구 사항을 충족하는지 확인 합니다.  
  
## 멤버  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[VerifyInterfaceHelper::Verify 메서드](../windows/verifyinterfacehelper-verify-method.md)||  
  
## 상속 계층  
 `VerifyInterfaceHelper`  
  
## 요구 사항  
 **헤더:** implements.h  
  
 **네임스페이스**Microsoft::WRL::Details  
  
## 참고 항목  
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)