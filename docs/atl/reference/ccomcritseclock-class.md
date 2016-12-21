---
title: "CComCritSecLock Class | Microsoft Docs"
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
  - "ATL::CComCritSecLock"
  - "ATL.CComCritSecLock<TLock>"
  - "ATL::CComCritSecLock<TLock>"
  - "ATL.CComCritSecLock"
  - "CComCritSecLock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComCritSecLock class"
ms.assetid: 223152a1-86c3-4ef9-89a7-f455fe791b0e
caps.latest.revision: 19
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CComCritSecLock Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 잠금 및 중요 섹션 개체를 잠금 해제 하는 방법을 제공 합니다.  
  
## 구문  
  
```  
  
      template<  
   class TLock  
> class CComCritSecLock  
```  
  
#### 매개 변수  
 *TLock*  
 잠그고 잠금을 해제할 개체입니다.  
  
## Members  
  
### Public 생성자  
  
|이름|설명|  
|--------|--------|  
|[CComCritSecLock::CComCritSecLock](../Topic/CComCritSecLock::CComCritSecLock.md)|생성자입니다.|  
|[CComCritSecLock::~CComCritSecLock](../Topic/CComCritSecLock::~CComCritSecLock.md)|소멸자|  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[CComCritSecLock::Lock](../Topic/CComCritSecLock::Lock.md)|잠글 임계 영역 개체에이 메서드를 호출 합니다.|  
|[CComCritSecLock::Unlock](../Topic/CComCritSecLock::Unlock.md)|임계 영역 개체의 잠금을 해제 하려면이 메서드를 호출 합니다.|  
  
## 설명  
 이 클래스를 사용할 때 보다 더 안전한 방식으로 개체를 잠금 해제 하는  [CComCriticalSection 클래스](../../atl/reference/ccomcriticalsection-class.md) 또는  [CComAutoCriticalSection 클래스](../../atl/reference/ccomautocriticalsection-class.md).  
  
## 요구 사항  
 **헤더:** atlbase.h  
  
## 참고 항목  
 [CComCriticalSection Class](../../atl/reference/ccomcriticalsection-class.md)   
 [CComAutoCriticalSection Class](../../atl/reference/ccomautocriticalsection-class.md)