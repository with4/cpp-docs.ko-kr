---
title: "CSecurityAttributes Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CSecurityAttributes"
  - "ATL::CSecurityAttributes"
  - "CSecurityAttributes"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSecurityAttributes class"
ms.assetid: a094880c-52e1-4a28-97ff-752d5869908e
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 27
---
# CSecurityAttributes Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 보안 특성 구조에 대 한 씬 래퍼입니다.  
  
> [!IMPORTANT]
>  런타임에서 Windows를 실행 하는 응용 프로그램에서이 클래스와 해당 멤버를 사용할 수 없습니다.  
  
## 구문  
  
```  
  
class CSecurityAttributes : public SECURITY_ATTRIBUTES  
  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CSecurityAttributes::CSecurityAttributes](../Topic/CSecurityAttributes::CSecurityAttributes.md)|생성자입니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CSecurityAttributes::Set](../Topic/CSecurityAttributes::Set.md)|속성을 설정 하려면이 메서드를 호출 하는 `CSecurityAttributes` 개체입니다.|  
  
## 설명  
 **SECURITY\_ATTRIBUTES** 구조를 포함 한  [보안 설명자](http://msdn.microsoft.com/library/windows/desktop/aa379561) 개체를 만드는 데 사용 하 고이 구조를 지정 하 여 검색 핸들을 상속할 수 있는지 여부를 지정 합니다.  
  
 Windows에서 액세스 제어 모델에 대 한 소개를 참조 하십시오.  [액세스 제어](http://msdn.microsoft.com/library/windows/desktop/aa374860) 에 있는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## 상속 계층 구조  
 `SECURITY_ATTRIBUTES`  
  
 `CSecurityAttributes`  
  
## 요구 사항  
 **헤더:** atlsecurity.h  
  
## 참고 항목  
 [보안 샘플](../../top/visual-cpp-samples.md)   
 [SECURITY\_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560)   
 [security descriptor](http://msdn.microsoft.com/library/windows/desktop/aa379561)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [Security Global Functions](../../atl/reference/security-global-functions.md)