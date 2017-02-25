---
title: "Registry and TypeLib Global Functions | Microsoft Docs"
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
helpviewer_keywords: 
  - "RegistryDataExchange function, 전역 함수"
ms.assetid: d58b8a4e-975c-4417-8b34-d3c847f679b3
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# Registry and TypeLib Global Functions
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이러한 함수 로드 및 형식 라이브러리를 등록 하는 방법에 대 한 지원을 제공 합니다.  
  
> [!IMPORTANT]
>  다음 표에 나열 된 함수를 실행 하는 응용 프로그램에서 사용할 수 있는 [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
|||  
|-|-|  
|[AtlRegisterTypeLib](../Topic/AtlRegisterTypeLib.md)|이 함수는 형식 라이브러리를 등록 하 라고 합니다.|  
|[AtlUnRegisterTypeLib](../Topic/AtlUnRegisterTypeLib.md)|이 함수를 호출 하는 형식 라이브러리의 등록을 취소합니다|  
|[AtlLoadTypeLib](../Topic/AtlLoadTypeLib.md)|형식 라이브러리를 로드 하려면이 함수가 호출 됩니다.|  
|[AtlUpdateRegistryFromResourceD](../Topic/AtlUpdateRegistryFromResourceD.md)|제공 된 리소스에서 레지스트리를 업데이트 하려면이 함수가 호출 됩니다.|  
|[RegistryDataExchange](../Topic/RegistryDataExchange.md)|이 함수를 읽거나 시스템 레지스트리에 쓸 라고 합니다.  호출는  [레지스트리 데이터 교환 매크로](../../atl/reference/registry-data-exchange-macros.md).|  
  
 이러한 함수는 노드 정보를 저장 하는 프로그램을 사용 하 여 레지스트리에서 제어 합니다.  
  
|||  
|-|-|  
|[AtlGetPerUserRegistration](../Topic/AtlGetPerUserRegistration.md)|검색 응용 프로그램 레지스트리 액세스를 리디렉션합니다 여부는 **HKEY\_CURRENT\_USER** \(**HKCU**\) 노드.|  
|[AtlSetPerUserRegistration](../Topic/AtlSetPerUserRegistration.md)|응용 프로그램 레지스트리 액세스를 리디렉션합니다 여부를 설정 하는 **HKEY\_CURRENT\_USER** \(**HKCU**\) 노드.|  
  
## 참고 항목  
 [함수](../../atl/reference/atl-functions.md)