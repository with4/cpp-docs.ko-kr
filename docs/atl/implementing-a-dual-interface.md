---
title: 이중 인터페이스 (ATL)를 구현할 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDispatchImpl class, implementing dual interfaces
- dual interfaces, implementing
ms.assetid: d1da3633-b445-4dcd-8a0a-3efdafada3ea
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 34cc55e4466dba094bf70e734340b40237207f3c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32356734"
---
# <a name="implementing-a-dual-interface"></a>이중 인터페이스를 구현합니다.
사용 하 여 이중 인터페이스를 구현할 수는 [IDispatchImpl](../atl/reference/idispatchimpl-class.md) 클래스의 기본 구현을 제공 하는 `IDispatch` 이중 인터페이스에서 메서드. 자세한 내용은 [Implementing the IDispatch Interface](http://msdn.microsoft.com/en-us/0e171f7f-0022-4e9b-ac8e-98192828e945)을 참조하십시오.  
  
 이 클래스를 사용 합니다.  
  
-   형식 라이브러리의 이중 인터페이스를 정의 합니다.  
  
-   특수화에서 클래스를 파생 `IDispatchImpl` (템플릿 인수로 인터페이스 및 형식 라이브러리에 대 한 정보를 전달).  
  
-   (또는 항목)을 통해 이중 인터페이스를 표시 하도록 COM 맵에 추가 `QueryInterface`합니다.  
  
-   클래스에서 인터페이스의 vtable 부분을 구현 합니다.  
  
-   런타임 시 인터페이스 정의 포함 하는 형식 라이브러리를 개체에 사용할 수 있는지 확인 합니다.  
  
## <a name="atl-simple-object-wizard"></a>ATL 단순 개체 마법사  
 새 인터페이스와 구현 하는 새 클래스를 만들려는 경우 사용할 수 있습니다는 [ATL 클래스 추가 대화 상자](../ide/add-class-dialog-box.md), 한 다음은 [ATL 단순 개체 마법사](../atl/reference/atl-simple-object-wizard.md)합니다.  
  
## <a name="implement-interface-wizard"></a>인터페이스 구현 마법사  
 기존 인터페이스를 사용 하도록 설정한 경우 사용할 수 있습니다는 [인터페이스 구현 마법사](../atl/reference/adding-a-new-interface-in-an-atl-project.md) 를 기존 클래스에 필요한 기본 클래스, COM 맵 엔트리 및 뼈대 메서드 구현을 추가 합니다.  
  
> [!NOTE]
>  형식 라이브러리의 주 및 부 버전 번호를 템플릿 인수로 전달 되도록 생성된 된 기본 클래스를 조정 해야 할 수 있습니다 프로그램 `IDispatchImpl` 기본 클래스입니다. 형식 라이브러리 버전 번호 인터페이스 구현 마법사 검사 하지 않습니다.  
  
## <a name="implementing-idispatch"></a>IDispatch를 구현합니다.  
 사용할 수는 `IDispatchImpl` 기본 COM 맵에서 적절 한 항목을 지정 하 여는 dispinterface의 구현을 제공 하는 클래스 (사용 하는 [COM_INTERFACE_ENTRY2](reference/com-interface-entry-macros.md#com_interface_entry2) 또는 [COM_INTERFACE_ENTRY_IID](reference/com-interface-entry-macros.md#com_interface_entry_iid) 매크로)는 해당 하는 이중 인터페이스를 설명 하는 형식 라이브러리를 보유 합니다. 구현 하는 매우 일반적 이기는 `IDispatch` 예를 들어이 방식으로 인터페이스입니다. ATL 단순 개체 마법사 및 인터페이스 구현 마법사 구현 하려는 가정 둘 다 `IDispatch` 이러한 방식으로 이러한에 소요 됩니다 적절 한 항목 지도입니다.  
  
> [!NOTE]
>  ATL은 제공 된 [IDispEventImpl](../atl/reference/idispeventimpl-class.md) 및 [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md) 호환 되는 이중 인터페이스의 정의 포함 하는 형식 라이브러리를 요구 하지 않고 dispinterface를 구현 하려면 클래스.  
  
## <a name="see-also"></a>참고 항목  
 [이중 인터페이스 및 ATL](../atl/dual-interfaces-and-atl.md)

