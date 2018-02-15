---
title: QueryInterface | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- QueryInterface
dev_langs:
- C++
helpviewer_keywords:
- interfaces, pointers
- interfaces, availability
- QueryInterface method
ms.assetid: 62fce95e-aafa-4187-b50b-e6611b74c3b3
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ce14ebef3649cea78e8cf4315a62392cfa142152
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="queryinterface"></a>QueryInterface
기본 COM 메커니즘은 사용 하는 개체 정적으로 (인스턴스화하기 전에)를 제공 하는 기능이 표현할 수 있는 메커니즘에는 없지만 **IUnknown** 라는 메서드가 [QueryInterface ](http://msdn.microsoft.com/library/windows/desktop/ms682521).  
  
 모든 인터페이스에서 파생 된 **IUnknown**이므로 모든 인터페이스의 구현에 `QueryInterface`합니다. 구현과 관계 없이이 메서드를 호출자가 포인터 인터페이스의 IID를 사용 하는 개체를 쿼리 합니다. 개체가 해당 인터페이스를 지원 하면 `QueryInterface` 인터페이스에 대 한 포인터도 호출 하는 동안 검색 `AddRef`합니다. 그렇지 않으면 반환 된 **E_NOINTERFACE** 오류 코드입니다.  
  
 준수 해야 하는 참고 [참조 횟수](../atl/reference-counting.md) 항상 규칙입니다. 호출 하는 경우 **릴리스** 참조 횟수를 0으로 감소 시키기 위해 인터페이스 포인터에 사용해 서는 안 해당 포인터 다시 합니다. 경우에 따라 개체에 대 한 약한 참조를 가져올 해야 할 수 있습니다 (즉, 해 볼 수의 참조 횟수를 증가 하지 않고 인터페이스 중 하나에 대 한 포인터를 가져오는)를 호출 하 여이 작업을 수행할 수 있지만 `QueryInterface` 이어서  **릴리스**합니다. 이러한 방식으로 얻은 포인터를 잘못 되었으며 사용할 수 없습니다. 이 더 쉽게 드러납니다 때 [_ATL_DEBUG_INTERFACES](reference/debugging-and-error-reporting-macros.md#_atl_debug_interfaces) 이 매크로 정의 하는 것은 찾기 참조 버그를 계산 하는 데 도움이 되므로 정의 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [COM 소개](../atl/introduction-to-com.md)   
 [개체에서 QueryInterface: 탐색](http://msdn.microsoft.com/library/windows/desktop/ms687230)

