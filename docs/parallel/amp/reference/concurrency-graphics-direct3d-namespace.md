---
title: "Concurrency::graphics::direct3d 네임스페이스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "amp_graphics/Concurrency::graphics::direct3d"
  - "amp_short_vectors/Concurrency::graphics::direct3d"
dev_langs: 
  - "C++"
ms.assetid: be283331-07cf-46e4-91a1-e8aa85d4ec8e
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Concurrency::graphics::direct3d 네임스페이스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

[get\_texture](../Topic/get_texture%20Function.md) 및 [make\_texture](../Topic/make_texture%20Function.md) 방법을 제공합니다.  
  
## 구문  
  
```  
namespace direct3d;  
```  
  
## 멤버  
  
### 함수  
  
|Name|설명|  
|----------|--------|  
|[get\_sampler 함수](../Topic/get_sampler%20Function.md)|지정된 샘플러 개체를 나타내는 제공된 액셀러레이터 보기에 대한 Direct3D 샘플러 상태 인터페이스를 가져옵니다.|  
|[get\_texture 함수](../Topic/get_texture%20Function.md)|지정된 [텍스처](../../../parallel/amp/reference/texture-class.md) 개체 내부 Direct3D 텍스처 인터페이스를 가져옵니다|  
|[make\_sampler 함수](../Topic/make_sampler%20Function.md)|Direct3D 샘플러 상태 인터페이스 포인터에서 샘플러를 만듭니다.|  
|[make\_texture 함수](../Topic/make_texture%20Function.md)|지정된 매개 변수를 사용하여 [texture](../../../parallel/amp/reference/texture-class.md) 개체를 만듭니다.|  
|[msad4 함수](../Topic/msad4%20Function.md)|4바이트 참조 값과 8바이트 소스 값을 비교하고 4개 합계의 벡터를 누적합니다.|  
  
## 요구 사항  
 **헤더:** amp\_graphics.h  
  
 **네임스페이스:** Concurrency::graphics  
  
## 참고 항목  
 [Concurrency::graphics 네임스페이스](../../../parallel/amp/reference/concurrency-graphics-namespace.md)