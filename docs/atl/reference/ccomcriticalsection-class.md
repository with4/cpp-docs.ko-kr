---
title: "CComCriticalSection Class | Microsoft Docs"
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
  - "ATL.CComCriticalSection"
  - "CComCriticalSection"
  - "ATL::CComCriticalSection"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComCriticalSection class"
ms.assetid: 44e1edd2-90be-4bfe-9739-58e8b419e7d1
caps.latest.revision: 21
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CComCriticalSection Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스 가져오고 중요 섹션 개체의 소유권을 해제 하는 메서드를 제공 합니다.  
  
## 구문  
  
```  
  
class CComCriticalSection  
  
```  
  
## Members  
  
### Public 생성자  
  
|이름|설명|  
|--------|--------|  
|[CComCriticalSection::CComCriticalSection](../Topic/CComCriticalSection::CComCriticalSection.md)|생성자입니다.|  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[CComCriticalSection::Init](../Topic/CComCriticalSection::Init.md)|만들고 임계 영역 개체를 초기화 합니다.|  
|[CComCriticalSection::Lock](../Topic/CComCriticalSection::Lock.md)|임계 영역 개체의 소유권을 가져옵니다.|  
|[CComCriticalSection::Term](../Topic/CComCriticalSection::Term.md)|중요 섹션 개체에 의해 사용 되는 시스템 리소스를 해제 합니다.|  
|[CComCriticalSection::Unlock](../Topic/CComCriticalSection::Unlock.md)|임계 영역 개체의 소유권을 해제합니다.|  
  
### 공용 데이터 멤버  
  
|이름|설명|  
|--------|--------|  
|[CComCriticalSection::m\_sec](../Topic/CComCriticalSection::m_sec.md)|A  **CRITICAL\_SECTION** 개체입니다.|  
  
## 설명  
 `CComCriticalSection`클래스에는 유사한  [CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md), 명시적으로 초기화 하 고 중요 섹션을 해제 해야 된다는.  
  
 일반적으로 사용 `CComCriticalSection` 통해는 `typedef` 이름  [CriticalSection](../Topic/CComMultiThreadModel::CriticalSection.md).  이 이름을 참조 `CComCriticalSection` 때  [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) 사용 중입니다.  
  
 참조  [CComCritSecLock 클래스](../../atl/reference/ccomcritseclock-class.md) 전화 보다이 클래스를 사용 하는 안전한 방법에 대 한 `Lock` 및 `Unlock` 직접.  
  
## 요구 사항  
 **헤더:**  atlcore.h  
  
## 참고 항목  
 [CComFakeCriticalSection Class](../../atl/reference/ccomfakecriticalsection-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [CComCritSecLock Class](../../atl/reference/ccomcritseclock-class.md)