---
title: ATL 창 특성 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- window traits
ms.assetid: c90cf850-9e91-49da-9cf3-ad4efb30347d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 71fbf5b3c4c3f1aa95070cbc0d30beb9e1321348
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32362370"
---
# <a name="understanding-window-traits"></a>창 특성 이해
창 특성 클래스는 ATL 창 개체 만들기에 사용 되는 스타일을 표준화 하기 위한 간단한 방법을 제공 합니다. 창 특성에서 템플릿 매개 변수로 허용 됩니다 [CWindowImpl](../atl/reference/cwindowimpl-class.md) 및 기본 창 스타일 클래스 수준에서 제공 하는 방법으로 다른 ATL 창 클래스입니다.  
  
 창 인스턴스를 만든 스타일에 대 한 호출에서 명시적으로 제공 하지 않는 경우 [만들기](../atl/reference/cwindowimpl-class.md#create)를 특성 클래스를 사용 하 여 창이 올바른 스타일으로 만들어집니다 계속 되도록 합니다. 특정 스타일으로 설정 되어 있는지 해당 창 클래스의 모든 인스턴스에 대 한 다른 스타일을 허용 하는 동안 인스턴스 당 단위로 설정할 수도 확인할 수 있습니다.  
  
## <a name="atl-window-traits-templates"></a>ATL 창 특성 템플릿  
 ATL은 템플릿 매개 변수를 사용 하 여 컴파일 타임에 기본 스타일을 설정할 수 있도록 하는 두 개의 창 특성 템플릿을 제공 합니다.  
  
|클래스|설명|  
|-----------|-----------------|  
|[CWinTraits](../atl/reference/cwintraits-class.md)|창 스타일 없음 다른 스타일에 대 한 호출에 지정 된 경우에 사용할 수 있는 기본 제공 하려는 경우이 서식 파일을 사용 하 여 **만들기**합니다. 설정 된 스타일 보다 우선 적용 실행된 시간에 제공 되는 스타일 컴파일 시간입니다.|  
|[CWinTraitsOR](../atl/reference/cwintraitsor-class.md)|창 클래스에 대해 항상 설정 되어 있어야 하는 스타일을 지정 하려는 경우에이 클래스를 사용 합니다. 런타임 시 제공 되는 스타일 비트 OR 연산자를 사용 하 여 컴파일 타임에 설정 된 스타일과 결합 됩니다.|  
  
 ATL 이러한 서식 파일 뿐 아니라 다양 한 미리 정의 된 특수화를 제공는 `CWinTraits` 창 스타일의 자주 사용 되는 조합에 대 한 서식 파일입니다. 참조는 [용으로 CWinTraits](../atl/reference/cwintraits-class.md) 대 한 자세한 내용은 설명서를 참조 합니다.  
  
## <a name="custom-window-traits"></a>사용자 지정 창 특성  
 ATL에 제공 된 템플릿 중 하나는 특수화 드문 경우에 충분 하지 및 사용자 지정 특성 클래스를 만들어야 할 두 개의 정적 함수를 구현 하는 클래스를 만들 필요가: `GetWndStyle` 및 **GetWndStyleEx** :  
  
 [!code-cpp[NVC_ATL_Windowing#68](../atl/codesnippet/cpp/understanding-window-traits_1.h)]  
  
 새 스타일 값을 생성 하는 데 사용할 수 있는 런타임 시 일부 스타일 값 전달 됩니다 이러한 각 함수. 이 정적 함수에 전달 된 스타일 값에 대 한 스타일 인수로 전달 되는 항목 됩니다 창 특성 클래스가 ATL 창 클래스의 템플릿 인수로 사용 중인 경우 [만들기](../atl/reference/cwindowimpl-class.md#create)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [창 클래스](../atl/atl-window-classes.md)

