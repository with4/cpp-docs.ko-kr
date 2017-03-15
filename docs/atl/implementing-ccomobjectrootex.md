---
title: "Implementing CComObjectRootEx | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CComObjectRootEx"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComObjectRoot class, 구현"
  - "CComObjectRootEx class"
ms.assetid: 79630c44-f2df-4e9e-b730-400a0ebfbd2b
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Implementing CComObjectRootEx
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[CComObjectRootEx](../atl/reference/ccomobjectrootex-class.md)는 필수 항목이며, 모든 ATL 개체의 상속에는 `CComObjectRootEx` 또는 [CComObjectRoot](../atl/reference/ccomobjectroot-class.md) 인스턴스 하나가 있어야 합니다.  `CComObjectRootEx`에서는 COM 맵 엔트리를 기반으로 하는 기본 `QueryInterface` 메커니즘을 제공합니다.  
  
 클라이언트가 인터페이스를 쿼리하면 COM 맵을 통해 개체의 인터페이스가 클라이언트에 표시됩니다.  쿼리는 `CComObjectRootEx::InternalQueryInterface`를 통해 수행됩니다.  `InternalQueryInterface`에서는 COM 맵 테이블의 인터페이스만 처리됩니다.  
  
 [COM\_INTERFACE\_ENTRY](../Topic/COM_INTERFACE_ENTRY%20\(ATL\).md) 매크로 또는 해당 변형 중 하나를 사용하여 인터페이스를 COM 맵 테이블에 입력할 수 있습니다.  예를 들어 다음 코드는 `IDispatch`, `IBeeper` 및 `ISupportErrorInfo` 인터페이스를 COM 맵 테이블에 입력합니다.  
  
 [!code-cpp[NVC_ATL_COM#1](../atl/codesnippet/CPP/implementing-ccomobjectrootex_1.h)]  
  
## 참고 항목  
 [Fundamentals of ATL COM Objects](../atl/fundamentals-of-atl-com-objects.md)   
 [COM Map Macros](../atl/reference/com-map-macros.md)