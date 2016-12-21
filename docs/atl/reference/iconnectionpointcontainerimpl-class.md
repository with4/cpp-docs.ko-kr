---
title: "IConnectionPointContainerImpl Class | Microsoft Docs"
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
  - "ATL::IConnectionPointContainerImpl"
  - "ATL.IConnectionPointContainerImpl"
  - "ATL.IConnectionPointContainerImpl<T>"
  - "IConnectionPointContainerImpl"
  - "ATL::IConnectionPointContainerImpl<T>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "connectable objects"
  - "연결 지점[C++], container"
  - "IConnectionPointContainerImpl class"
ms.assetid: 10db5a8d-8be9-4d9d-8a82-8ab9ffe3e9d6
caps.latest.revision: 19
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IConnectionPointContainerImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 컬렉션을 관리 하는 연결 지점 컨테이너 구현  [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) 개체입니다.  
  
## 구문  
  
```  
  
      template<  
   class T   
>  
class ATL_NO_VTABLE IConnectionPointContainerImpl :   
   public IConnectionPointContainer  
```  
  
#### 매개 변수  
 `T`  
 파생 클래스에서 `IConnectionPointContainerImpl`.  
  
## Members  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[IConnectionPointContainerImpl::EnumConnectionPoints](../Topic/IConnectionPointContainerImpl::EnumConnectionPoints.md)|연결점이 있는 연결 가능한 개체에서 지원 되는 반복 하는 열거자를 만듭니다.|  
|[IConnectionPointContainerImpl::FindConnectionPoint](../Topic/IConnectionPointContainerImpl::FindConnectionPoint.md)|지정한 IID를 지 원하는 연결 지점에 대 한 인터페이스 포인터를 검색 합니다.|  
  
## 설명  
 `IConnectionPointContainerImpl`컬렉션을 관리 하는 연결 지점 컨테이너 구현  [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) 개체입니다.  `IConnectionPointContainerImpl`연결 가능 개체에 대 한 자세한 정보를 검색 하는 클라이언트를 호출할 수 있습니다 두 가지 방법을 제공 합니다.  
  
-   `EnumConnectionPoints`클라이언트를 보내는 개체가 지 원하는 인터페이스를 확인할 수 있습니다.  
  
-   `FindConnectionPoint`개체 특정 송신 인터페이스를 지원 하는지 여부를 확인 하는 클라이언트를 허용 합니다.  
  
 ATL 연결 지점 사용에 대 한 자세한 내용은  [연결점](../../atl/atl-connection-points.md).  
  
## 상속 계층 구조  
 `IConnectionPointContainer`  
  
 `IConnectionPointContainerImpl`  
  
## 요구 사항  
 **헤더:**  atlcom.h  
  
## 참고 항목  
 [IConnectionPointContainer](http://msdn.microsoft.com/library/windows/desktop/ms683857)   
 [Class Overview](../../atl/atl-class-overview.md)