---
title: "CComAutoDeleteCriticalSection Class | Microsoft Docs"
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
  - "ATL.CComAutoDeleteCriticalSection"
  - "CComAutoDeleteCriticalSection"
  - "ATL::CComAutoDeleteCriticalSection"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComAutoDeleteCriticalSection class"
ms.assetid: 2396dbea-1c60-4841-b50e-c4e18af311a3
caps.latest.revision: 17
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CComAutoDeleteCriticalSection Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스 가져오고 중요 섹션 개체의 소유권을 해제 하는 메서드를 제공 합니다.  
  
## 구문  
  
```  
  
class CComAutoDeleteCriticalSection : public CComSafeDeleteCriticalSection  
  
```  
  
## 설명  
 `CComAutoDeleteCriticalSection`파생 클래스에서  [CComSafeDeleteCriticalSection](../../atl/reference/ccomsafedeletecriticalsection-class.md).  그러나 `CComAutoDeleteCriticalSection` 재정의  [용어](../Topic/CComSafeDeleteCriticalSection::Term.md) 메서드에 `private` 강제로 내부 메모리 정리만 때이 클래스의 인스턴스가 범위를 벗어나면 또는 명시적으로 메모리에서 삭제 됩니다 발생 하는 액세스 합니다.  
  
 이 클래스를 통해 기본 클래스 메서드가 추가 소개합니다.  참조  [CComSafeDeleteCriticalSection](../../atl/reference/ccomsafedeletecriticalsection-class.md) 및  [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md) 임계 도우미 클래스에 대 한 자세한 내용은.  
  
## 상속 계층 구조  
 [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)  
  
 [CComSafeDeleteCriticalSection](../../atl/reference/ccomsafedeletecriticalsection-class.md)  
  
 `CComAutoDeleteCriticalSection`  
  
## 요구 사항  
 **헤더:**  atlcore.h  
  
## 참고 항목  
 [CComSafeDeleteCriticalSection Class](../../atl/reference/ccomsafedeletecriticalsection-class.md)   
 [CComCriticalSection Class](../../atl/reference/ccomcriticalsection-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)