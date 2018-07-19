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
ms.openlocfilehash: ace347148f3a339c75fd9a1069be368c7373d351
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38952931"
---
# <a name="multiple-dual-interfaces"></a>여러 개의 이중 인터페이스
이중 인터페이스 (즉, vtable 및 런타임에 바인딩, 따라서 클래스를 사용할 수 있도록 스크립팅 언어 뿐 아니라 c + + 모두의 유연성)의 장점을 결합 하려는 경우 다중 상속 하는 데 사용 합니다.  
  
 단일 COM 개체에서 여러 개의 이중 인터페이스를 노출할 수 있지만 권장 되지 않습니다. 여러 개의 이중 인터페이스의 경우 있어야 하나만 `IDispatch` 인터페이스를 노출 합니다. 대/소문자 인지 확인 하십시오. 사용할 수 있는 기법 처벌을 받을 함수 또는 향상 된 코드 복잡성의 손실 등을 수행 합니다. 이 방법을 사용을 고려 하는 개발자는 장점 및 단점에 신중 하 게 평가 해야 합니다.  
  
## <a name="exposing-a-single-idispatch-interface"></a>단일 IDispatch 인터페이스를 노출합니다.  
 두 개 이상의 특수화에서 파생 하 여 단일 개체에 대해 여러 개의 이중 인터페이스를 노출 하는 것이 불가능 `IDispatchImpl`합니다. 그러나 클라이언트에 대 한 쿼리를 허용 하는 경우는 `IDispatch` 인터페이스를 사용 해야 합니다 [COM_INTERFACE_ENTRY2](reference/com-interface-entry-macros.md#com_interface_entry2) 매크로 (또는 [COM_INTERFACE_ENTRY_IID](reference/com-interface-entry-macros.md#com_interface_entry_iid)))에 사용할 기본 클래스를 지정 하는 구현의 `IDispatch`합니다.  
  
 [!code-cpp[NVC_ATL_COM#23](../atl/codesnippet/cpp/multiple-dual-interfaces_1.h)]  
  
 때문에 하나만 `IDispatch` 인터페이스를 노출 하는 개체를 통해 액세스할 수 있는 클라이언트는 `IDispatch` 인터페이스 메서드 또는 다른 모든 인터페이스의 속성에 액세스할 수 없게 됩니다.  
  
## <a name="combining-multiple-dual-interfaces-into-a-single-implementation-of-idispatch"></a>여러 개의 이중 인터페이스를 IDispatch의 단일 구현이 결합  
 ATL은 여러 개의 이중 인터페이스의 단일 구현이 결합에 대 한 모든 지원을 제공 하지 않습니다 `IDispatch`합니다. 그러나 몇 가지 알려진된 방법이 수동으로 별도의 통합을 포함 하는 템플릿 기반 클래스 만들기와 같은 인터페이스를 결합 하 `IDispatch` 인터페이스를 수행 하려면 새 개체 만들기는 `QueryInterface` 함수 또는 사용 하는 typeinfo 기반 구현의 만들려면 중첩 된 개체는 `IDispatch` 인터페이스입니다.  
  
 이러한 접근 방식은 문제가 네임 스페이스 충돌 가능성이 뿐만 아니라 코드 복잡성 및 유지 관리 합니다. 여러 개의 이중 인터페이스를 만드는 권장 되지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [이중 인터페이스 및 ATL](../atl/dual-interfaces-and-atl.md)

