---
title: "Security Global Functions | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ACL object global functions"
  - "security IDs [C++]"
  - "SIDs [C++], modifying SID objects"
ms.assetid: 6a584bfe-16b7-47f4-8439-9c789c41567a
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Security Global Functions
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이러한 함수 개체 SID와 ACL을 수정 하는 기능을 지원 합니다.  
  
> [!IMPORTANT]
>  다음 표에 나열 된 함수를 실행 하는 응용 프로그램에서 사용할 수 있는 [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
|||  
|-|-|  
|[AtlGetDacl](../Topic/AtlGetDacl.md)|지정 된 개체의 임의 액세스 제어 목록 \(DACL\) 정보를 검색 하려면이 함수를 호출 합니다.|  
|[AtlSetDacl](../Topic/AtlSetDacl.md)|지정 된 개체의 임의 액세스 제어 목록 \(DACL\) 정보를 설정 하려면이 함수를 호출 합니다.|  
|[AtlGetGroupSid](../Topic/AtlGetGroupSid.md)|그룹 보안 식별자 \(SID\)를 개체를 검색 하려면이 함수를 호출 합니다.|  
|[AtlSetGroupSid](../Topic/AtlSetGroupSid.md)|그룹 보안 식별자 \(SID\)를 개체를 설정 하려면이 함수를 호출 합니다.|  
|[AtlGetOwnerSid](../Topic/AtlGetOwnerSid.md)|개체의 소유자 보안 식별자 \(SID\) 검색 하려면이 함수를 호출 합니다.|  
|[AtlSetOwnerSid](../Topic/AtlSetOwnerSid.md)|개체의 소유자 보안 식별자 \(SID\)를 설정 하려면이 함수를 호출 합니다.|  
|[AtlGetSacl](../Topic/AtlGetSacl.md)|지정 된 개체의 시스템 액세스 제어 목록 \(SACL\) 정보를 검색 하려면이 함수를 호출 합니다.|  
|[AtlSetSacl](../Topic/AtlSetSacl.md)|지정 된 개체의 시스템 액세스 제어 목록 \(SACL\) 정보를 설정 하려면이 함수를 호출 합니다.|  
|[AtlGetSecurityDescriptor](../Topic/AtlGetSecurityDescriptor.md)|지정 된 개체의 보안 설명자를 검색 하려면이 함수를 호출 합니다.|  
  
## 참고 항목  
 [함수](../../atl/reference/atl-functions.md)