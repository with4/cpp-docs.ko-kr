---
title: 옵션, ATL 컨트롤 마법사 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.codewiz.class.atl.control.options
dev_langs:
- C++
helpviewer_keywords:
- ATL Control Wizard, options
ms.assetid: 4607c51a-992d-433e-9281-919c6f519a3d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ab1062d32aadc2ec4af68cda8bca02ac1a45a526
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32364475"
---
# <a name="options-atl-control-wizard"></a>옵션, ATL 컨트롤 마법사
여기에 요약 "검색 결과"를 삽입 합니다.  
  
 마법사의이 페이지를 사용 하 여 만들고 컨트롤의 형식 및 인터페이스를 지 원하는 포함의 수준을 정의 합니다.  
  
## <a name="uielement-list"></a>UI 요소 목록  
 **컨트롤 형식**  
 만들 컨트롤의 종류입니다.  
  
-   **표준 제어:는 ActiveX 컨트롤입니다.**  
  
-   **복합 컨트롤**:는 ActiveX 컨트롤 (대화 상자와 유사)를 포함할 수 있는 다른 ActiveX 컨트롤 또는 Windows 컨트롤입니다. 복합 컨트롤에는 다음이 포함 되어 있습니다.  
  
    -   복합 컨트롤을 구현 하는 대화 상자에 대 한 템플릿.  
  
    -   사용자 지정 리소스 레지스트리 합성 컨트롤 호출 될 때 자동으로 등록 합니다.  
  
    -   복합 컨트롤을 구현 하는 c + + 클래스입니다.  
  
    -   복합 컨트롤에 의해 노출 되는 COM 인터페이스입니다.  
  
    -   복합 컨트롤을 포함 하는 HTML 테스트 페이지  
  
     기본적으로이 컨트롤 설정 [CComControlBase::m_bWindowOnly](../../atl/reference/ccomcontrolbase-class.md#m_bwindowonly) 를 true 창 있는 컨트롤 임을 나타냅니다. 싱크 맵을 구현합니다. 자세한 내용은 참조 [DHTML 컨트롤에 대 한 지원을](../../atl/atl-support-for-dhtml-controls.md)합니다.  
  
-   **DHTML 컨트롤**:는 ATL DHTML 컨트롤에 HTML을 사용 하 여 사용자 인터페이스를 지정 합니다. DHTML UI 클래스는 com을 포함합니다. 기본적으로이 컨트롤 설정 [CComControlBase::m_bWindowOnly](../../atl/reference/ccomcontrolbase-class.md#m_bwindowonly) 를 true 창 있는 컨트롤 임을 나타냅니다.  
  
     자세한 내용은 참조 [DHTML 컨트롤 프로젝트의 요소를 식별](../../atl/identifying-the-elements-of-the-dhtml-control-project.md)합니다.  
  
 **최소 컨트롤**  
 대부분의 컨테이너에서 반드시 필요로 하는 인터페이스를 지원 합니다. 설정할 수 있습니다 **최소 컨트롤** 컨트롤 형식에 대 한: 최소 표준 컨트롤, 최소 복합 컨트롤을 또는 최소 DHTML 컨트롤을 만들 수 있습니다.  
  
 **집계**  
 만들 컨트롤에 대 한 집계 지원을 추가 합니다. 자세한 내용은 참조 [집계](../../atl/aggregation.md)합니다.  
  
-   **예**: 집계할 수 있는 컨트롤을 만듭니다.  
  
-   **더**: 집계 될 수 없는 컨트롤을 만듭니다.  
  
-   **만**: 집계를 통해 인스턴스화할 수 있는 컨트롤을 만듭니다.  
  
 **스레딩 모델**  
 컨트롤에서 사용 되는 스레딩 모델을 지정 합니다.  
  
-   **단일**: 컨트롤은 기본 COM 스레드에서만에서 실행 됩니다.  
  
-   **아파트**: 모든 단일 스레드 아파트에서 컨트롤을 만들 수 있습니다. 기본값입니다.  
  
 **Interface**  
 이 컨트롤의 컨테이너를 제공 하는 인터페이스의 형식입니다.  
  
-   **이중**: 속성 및 메서드를 통해 노출 하는 인터페이스를 만들고 `IDispatch` 및는 VTBL를 통해 직접 합니다.  
  
-   **사용자 지정**: VTBL 통해 직접 메서드를 노출 하는 인터페이스를 만듭니다.  
  
     선택 하는 경우 **사용자 지정**, 컨트롤을 지정할 수 있습니다 **자동화 호환**합니다. 선택 하는 경우 **자동화 호환**, 다음 마법사 추가 [oleautomation](../../windows/oleautomation.md) 특성을 인터페이스는 IDL에 및 인터페이스 oleaut32.dll에 유니버설 마샬러에서 마샬링할 수 있습니다. 참조 [마샬링 정보](http://msdn.microsoft.com/library/windows/desktop/ms692621) 자세한 내용은 Windows sdk입니다.  
  
     또한 선택 하는 경우 **자동화 호환**, 컨트롤의 모든 메서드에 대 한 모든 매개 변수 여야 합니다 **VARIANT** 호환 됩니다.  
  
 **지원**  
 컨트롤에 대 한 기타 추가 지원을 설정합니다.  
  
-   **연결 지점**: 개체의 클래스에서 파생 하 여 개체에 대 한 연결점을 사용 하면 [IConnectionPointContainerImpl](../../atl/reference/iconnectionpointcontainerimpl-class.md) 하므로 소스 인터페이스를 노출 하 고 있습니다.  
  
-   **사용이 허가 된**: 컨트롤에 대 한 지원 추가 [라이선스](http://msdn.microsoft.com/library/windows/desktop/ms690543)합니다. 클라이언트 컴퓨터에 정확한 라이선스 사용이 허가 된 컨트롤 에서만 호스팅할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [ATL 컨트롤 마법사](../../atl/reference/atl-control-wizard.md)

