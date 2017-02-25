---
title: "CComObjectNoLock Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CComObjectNoLock"
  - "ATL::CComObjectNoLock"
  - "ATL.CComObjectNoLock<Base>"
  - "CComObjectNoLock"
  - "ATL::CComObjectNoLock<Base>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComObjectNoLock class"
ms.assetid: 288c6506-7da8-4127-8d58-7f4bd779539a
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CComObjectNoLock Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 구현  **IUnknown** 의 집합체, 되지만 생성자에서 모듈 잠금 횟수를 증가 하지.  
  
## 구문  
  
```  
  
      template<  
   class Base   
>  
class CComObjectNoLock :  
   public Base  
```  
  
#### 매개 변수  
 `Base`  
 파생 클래스에서  [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) 또는  [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), 개체에서 지 원하는 다른 인터페이스 이름으로 원하는 대로.  
  
## Members  
  
### Public 생성자  
  
|이름|설명|  
|--------|--------|  
|[CComObjectNoLock::CComObjectNoLock](../Topic/CComObjectNoLock::CComObjectNoLock.md)|생성자입니다.|  
|[CComObjectNoLock::~CComObjectNoLock](../Topic/CComObjectNoLock::~CComObjectNoLock.md)|소멸자|  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[CComObjectNoLock::AddRef](../Topic/CComObjectNoLock::AddRef.md)|개체의 참조 횟수를 증가 시킵니다.|  
|[CComObjectNoLock::QueryInterface](../Topic/CComObjectNoLock::QueryInterface.md)|요청 된 인터페이스에 포인터를 반환 합니다.|  
|[CComObjectNoLock::Release](../Topic/CComObjectNoLock::Release.md)|개체의 참조 횟수를 감소 시킵니다.|  
  
## 설명  
 `CComObjectNoLock`유사한  [CComObject](../../atl/reference/ccomobject-class.md) 구현 한다는 점에서  [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) 의 집합체입니다. 그러나 `CComObjectNoLock` 모듈 잠금을 증가 생성자에서 개수를 계산 하지.  
  
 ATL을 사용 하 여 `CComObjectNoLock` 클래스 팩터리를 내부적으로.  일반적으로이 클래스를 직접 사용 됩니다지 않습니다.  
  
## 상속 계층 구조  
 `Base`  
  
 `CComObjectNoLock`  
  
## 요구 사항  
 **헤더:**  atlcom.h  
  
## 참고 항목  
 [Class Overview](../../atl/atl-class-overview.md)