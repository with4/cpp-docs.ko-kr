---
title: "CAutoRevertImpersonation Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CAutoRevertImpersonation"
  - "CAutoRevertImpersonation"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAutoRevertImpersonation class"
ms.assetid: 43732849-1940-4bd4-9d52-7a5698bb8838
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CAutoRevertImpersonation Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스를 되돌리는  [CAccessToken](../../atl/reference/caccesstoken-class.md) nonimpersonating 상태로 범위를 벗어날 때 개체.  
  
## 구문  
  
```  
  
class CAutoRevertImpersonation  
  
```  
  
## Members  
  
### Public 생성자  
  
|이름|설명|  
|--------|--------|  
|[CAutoRevertImpersonation::CAutoRevertImpersonation](../Topic/CAutoRevertImpersonation::CAutoRevertImpersonation.md)|생성 된 `CAutoRevertImpersonation` 개체|  
|[CAutoRevertImpersonation::~CAutoRevertImpersonation](../Topic/CAutoRevertImpersonation::~CAutoRevertImpersonation.md)|개체를 소멸 시키고 액세스 토큰 가장을 되돌립니다.|  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[CAutoRevertImpersonation::Attach](../Topic/CAutoRevertImpersonation::Attach.md)|액세스 토큰에는 가장 조항이 자동화합니다.|  
|[CAutoRevertImpersonation::Detach](../Topic/CAutoRevertImpersonation::Detach.md)|자동 가장 조항이 취소합니다.|  
|[CAutoRevertImpersonation::GetAccessToken](../Topic/CAutoRevertImpersonation::GetAccessToken.md)|이 개체와 관련 된 액세스 토큰 현재를 검색 합니다.|  
  
## 설명  
 [액세스 토큰](http://msdn.microsoft.com/library/windows/desktop/aa374909) 프로세스 또는 스레드의 보안 컨텍스트를 설명 하 고 Windows NT 또는 Windows 2000 시스템에 로그온 한 각 사용자에 게 할당 되는 개체입니다.  이러한 액세스 토큰을 나타낼 수 있는 `CAccessToken` 클래스입니다.  
  
 액세스 토큰을 가장 하는 경우가 있습니다.  이 클래스는 편의 제공 하지만 가장 액세스 토큰을 수행 하지 않습니다. nonimpersonated 상태로 자동 조항이 수행 합니다.  가장 토큰 액세스 여러 가지 방법으로 수행할 수 있습니다.  
  
 Windows에서 액세스 제어 모델에 대 한 소개를 참조 하십시오.  [액세스 제어](http://msdn.microsoft.com/library/windows/desktop/aa374860) 에 있는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## 요구 사항  
 **헤더:** atlsecurity.h  
  
## 참고 항목  
 [ATLSecurity 샘플](../../top/visual-cpp-samples.md)   
 [Access Tokens](http://msdn.microsoft.com/library/windows/desktop/aa374909)   
 [Class Overview](../../atl/atl-class-overview.md)