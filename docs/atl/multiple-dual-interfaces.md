---
title: 여러 개의 이중 인터페이스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- multiple dual interfaces
- COM_INTERFACE_ENTRY2 macro
- dual interfaces, exposing multiple
- multiple dual interfaces, exposing with ATL
- IDispatchImpl class, multiple dual interfaces
- COM_INTERFACE_ENTRY_IID macro
ms.assetid: 7fea86e6-247f-4063-be6e-85588a9e3719
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e23682bd0b7c923a1e377463405f84a6c6ee1221
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32356721"
---
# <a name="multiple-dual-interfaces"></a>여러 개의 이중 인터페이스
이중 인터페이스 (즉, vtable 및 런타임에 바인딩, 따라서 클래스를 사용할 수 있도록 두 가지 스크립팅 언어 뿐만 아니라 c + +의 유연성)의 장점을 결합 하려는 경우 다중 상속 기법을 사용 합니다.  
  
 단일 COM 개체에 여러 개의 이중 인터페이스를 노출할 수 있지만 권장 되지 않습니다. 여러 개의 이중 인터페이스 인 있어야 하나만 `IDispatch` 인터페이스를 노출 합니다. 대/소문자 인지 확인 하십시오. 사용할 수 있는 기술을 저하 손실 함수 또는 증가 한 코드 복잡성 등을 수행 합니다. 이 방법을 고려 하는 개발자는 장점과 단점에 신중 하 게 저울질 해봐야 합니다.  
  
## <a name="exposing-a-single-idispatch-interface"></a>단일 IDispatch 인터페이스를 노출합니다.  
 두 개 이상의 특수화에서 파생 하 여 단일 개체에 여러 개의 이중 인터페이스를 노출 하는 것이 불가능 `IDispatchImpl`합니다. 그러나 클라이언트에 대 한 쿼리를 허용 하는 경우는 `IDispatch` 인터페이스를 사용 하도록 해야 합니다는 [COM_INTERFACE_ENTRY2](reference/com-interface-entry-macros.md#com_interface_entry2) 매크로 (또는 [COM_INTERFACE_ENTRY_IID](reference/com-interface-entry-macros.md#com_interface_entry_iid)))에 사용할 기본 클래스를 지정 하는 구현 `IDispatch`합니다.  
  
 [!code-cpp[NVC_ATL_COM#23](../atl/codesnippet/cpp/multiple-dual-interfaces_1.h)]  
  
 때문에 하나의 `IDispatch` 인터페이스를 노출 통해 개체에 액세스할 수 있는 클라이언트는 `IDispatch` 인터페이스는 메서드 또는 다른 모든 인터페이스의 속성에 액세스할 수 없습니다.  
  
## <a name="combining-multiple-dual-interfaces-into-a-single-implementation-of-idispatch"></a>여러 개의 이중 인터페이스를 IDispatch의 단일 구현이 결합  
 ATL 지원 하지 않는 모든의 단일 구현이에 여러 개의 이중 인터페이스를 결합 하는 데 `IDispatch`합니다. 그러나 수동으로 별도의 합집합을 포함 하는 템플릿 기반 클래스를 만들 때 처럼 인터페이스를 결합 하는 알려진된 답은 `IDispatch` 인터페이스를 수행 하려면 새 개체를 만드는 `QueryInterface` 함수 또는 사용 하는 중첩 된 개체를 만드는의 typeinfo 기반 구현에서 `IDispatch` 인터페이스입니다.  
  
 이러한 네임 스페이스 충돌 가능성이 뿐만 아니라 코드 복잡성 및 유지 관리 문제를 다 가져옵니다. 여러 개의 이중 인터페이스를 만드는 권장 되지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [이중 인터페이스 및 ATL](../atl/dual-interfaces-and-atl.md)

