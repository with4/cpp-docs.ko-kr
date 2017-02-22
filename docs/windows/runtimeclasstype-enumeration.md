---
title: "RuntimeClassType 열거형 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::RuntimeClassType"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RuntimeClassType 열거형"
ms.assetid: d380712d-672e-4ea9-b7c5-cf9fa7dbb770
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# RuntimeClassType 열거형
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

지원되는 [RuntimeClass](../windows/runtimeclass-class.md) 인스턴스의 형식을 지정합니다.  
  
## 구문  
  
```  
enum RuntimeClassType;  
```  
  
## 멤버  
  
### 값  
  
|Name|설명|  
|----------|--------|  
|`ClassicCom`|클래식 COM 런타임 클래스.|  
|`Delegate`|**ClassicCom**와 같습니다.|  
|`InhibitFtmBase`|`FtmBase` 는 `__WRL_CONFIGURATION_LEGACY__` 가 정의되지 않는 동안 해제됩니다.|  
|`InhibitWeakReference`|약한 참조를 지원하지 않습니다.|  
|`WinRt`|[!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] 클래스입니다.|  
|`WinRtClassicComMix`|`WinRt` 및 `ClassicCom`의 조합입니다.|  
  
## 요구 사항  
 **헤더:** implements.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [Microsoft::WRL 네임스페이스](../windows/microsoft-wrl-namespace.md)