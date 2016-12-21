---
title: "프로젝트의 스레딩 모델 지정(ATL) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ATL_APARTMENT_THREADED 매크로"
  - "_ATL_FREE_THREADED 매크로"
  - "_ATL_SINGLE_THREADED 매크로"
  - "ATL, 다중 스레딩"
  - "스레딩[ATL], 모델"
ms.assetid: 6b571078-521c-4f3e-9f08-482aa235a822
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 프로젝트의 스레딩 모델 지정(ATL)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

다음 매크로 ATL 프로젝트의 스레딩 모델 지정 가능 합니다.  
  
|매크로|사용 지침|  
|---------|-----------|  
|\_ATL\_SINGLE\_THREADED|모든 개체가 단일 스레딩 모델을 사용 하는 경우 정의 합니다.|  
|\_ATL\_APARTMENT\_THREADED|하나 이상의 개체가 아파트 스레딩을 사용 하는 경우 정의 합니다.|  
|\_ATL\_FREE\_THREADED|하나 이상의 개체가 자유 또는 중립 스레딩을 사용 하는 경우 정의 합니다.  기존 코드 참조에 해당 하는 매크로 포함할 수 있습니다  [\_ATL\_MULTI\_THREADED](../Topic/_ATL_MULTI_THREADED.md).|  
  
 \_Atl\_free\_threaded가이 매크로 중 하나를 프로젝트에 대 한 정의 하지 않은 경우에 적용 됩니다.  
  
 매크로 런타임 성능을 다음과 같은 영향을 줍니다.  
  
-   해당 프로젝트의 개체에 매크로 지정 하면 런타임 성능이 향상 됩니다.  
  
-   높은 수준의 모든 개체를 단일 스레드이기 \_atl\_apartment\_threaded를 지정 하는 경우 예를 들어, 매크로 지정 하는 런타임 성능이 약간 저하 됩니다.  
  
-   \_ATL\_SINGLE\_THREADED 하나를 지정 하거나 이상의 개체가 아파트 스레딩 또는 자유 스레딩, 사용 하는 경우의 예를 들어, 매크로 지정 응용 프로그램이 런타임에 실패할 수 발생할 수 있습니다.  
  
 참조  [ATL 단순 개체 마법사, 옵션](../atl/reference/options-atl-simple-object-wizard.md) 의 스레딩에 대 한 설명을 ATL 개체에 대해 사용할 수 있는 모델입니다.  
  
## 참고 항목  
 [개념](../atl/active-template-library-atl-concepts.md)