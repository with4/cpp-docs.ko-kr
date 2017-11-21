---
title: "CComObjectRootEx 구현 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CComObjectRootEx
dev_langs: C++
helpviewer_keywords:
- CComObjectRoot class, implementing
- CComObjectRootEx class
ms.assetid: 79630c44-f2df-4e9e-b730-400a0ebfbd2b
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 960f7989d3891be4cf23ef75b0982a2577f5e95e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="implementing-ccomobjectrootex"></a>CComObjectRootEx 구현
[CComObjectRootEx](../atl/reference/ccomobjectrootex-class.md) 필수적; 모든 ATL 개체의 인스턴스 하나가 있어야 합니다. `CComObjectRootEx` 또는 [CComObjectRoot](../atl/reference/ccomobjectroot-class.md) 의 상속에 있습니다. `CComObjectRootEx`에서는 COM 맵 엔트리를 기반으로 하는 기본 `QueryInterface` 메커니즘을 제공합니다.  
  
 클라이언트가 인터페이스를 쿼리하면 COM 맵을 통해 개체의 인터페이스가 클라이언트에 표시됩니다. 쿼리는 `CComObjectRootEx::InternalQueryInterface`를 통해 수행됩니다. `InternalQueryInterface`에서는 COM 맵 테이블의 인터페이스만 처리됩니다.  
  
 인터페이스를 COM 맵 테이블에 입력할 수는 [COM_INTERFACE_ENTRY](reference/com-interface-entry-macros.md#com_interface_entry) 매크로 또는 해당 변형 중 하나입니다. 예를 들어 다음 코드는 `IDispatch`, `IBeeper` 및 `ISupportErrorInfo` 인터페이스를 COM 맵 테이블에 입력합니다.  
  
 [!code-cpp[NVC_ATL_COM#1](../atl/codesnippet/cpp/implementing-ccomobjectrootex_1.h)]  
  
## <a name="see-also"></a>참고 항목  
 [ATL COM 개체의 기본 사항](../atl/fundamentals-of-atl-com-objects.md)   
 [COM 맵 매크로](../atl/reference/com-map-macros.md)

