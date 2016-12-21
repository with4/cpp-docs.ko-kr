---
title: "CComSafeDeleteCriticalSection Class | Microsoft Docs"
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
  - "CComSafeDeleteCriticalSection"
  - "ATL::CComSafeDeleteCriticalSection"
  - "ATL.CComSafeDeleteCriticalSection"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComSafeDeleteCriticalSection class"
ms.assetid: 4d2932c4-ba8f-48ec-8664-1db8bed01314
caps.latest.revision: 18
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CComSafeDeleteCriticalSection Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스 가져오고 중요 섹션 개체의 소유권을 해제 하는 메서드를 제공 합니다.  
  
## 구문  
  
```  
  
class CComSafeDeleteCriticalSection : public CComCriticalSection  
  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CComSafeDeleteCriticalSection::CComSafeDeleteCriticalSection](../Topic/CComSafeDeleteCriticalSection::CComSafeDeleteCriticalSection.md)|생성자입니다.|  
|[CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection](../Topic/CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection.md)|소멸자|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CComSafeDeleteCriticalSection::Init](../Topic/CComSafeDeleteCriticalSection::Init.md)|만들고 임계 영역 개체를 초기화 합니다.|  
|[CComSafeDeleteCriticalSection::Lock](../Topic/CComSafeDeleteCriticalSection::Lock.md)|임계 영역 개체의 소유권을 가져옵니다.|  
|[CComSafeDeleteCriticalSection::Term](../Topic/CComSafeDeleteCriticalSection::Term.md)|중요 섹션 개체에 의해 사용 되는 시스템 리소스를 해제 합니다.|  
  
### 데이터 멤버  
  
|||  
|-|-|  
|[m\_bInitialized](../Topic/CComSafeDeleteCriticalSection::m_bInitialized.md)|플래그 여부는 내부  **CRITICAL\_SECTION** 개체 초기화 되었습니다.|  
  
## 설명  
 `CComSafeDeleteCriticalSection`파생 클래스에서  [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md).  그러나 `CComSafeDeleteCriticalSection` 추가 안전 메커니즘을 통해 제공  [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md).  
  
 인스턴스의 경우 `CComSafeDeleteCriticalSection` 범위를 벗어나면 또는 명시적으로 여전히 유효한 경우 메모리에서 삭제, 내부 중요 섹션 개체는 자동으로 정리 됩니다.  또한는 [CComSafeDeleteCriticalSection::Term](../Topic/CComSafeDeleteCriticalSection::Term.md) 메서드는 종료 정상적으로 내부 중요 섹션 개체에 아직 할당 되지 않은 또는 메모리에서 이미 해제 된 경우.  
  
 참조  [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md) 임계 도우미 클래스에 대 한 자세한 내용은.  
  
## 상속 계층 구조  
 [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)  
  
 `CComSafeDeleteCriticalSection`  
  
## 요구 사항  
 **헤더:**  atlcore.h  
  
## 참고 항목  
 [CComCriticalSection Class](../../atl/reference/ccomcriticalsection-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)