---
title: "옵션, ATL 컨트롤 마법사 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "vc.codewiz.class.atl.control.options"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL 컨트롤 마법사, 옵션"
ms.assetid: 4607c51a-992d-433e-9281-919c6f519a3d
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# 옵션, ATL 컨트롤 마법사
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

여기에 "검색 결과" 요약을 삽입합니다.  
  
 마법사의 이 페이지에서는 만들려는 컨트롤의 형식과 컨트롤이 포함하는 인터페이스 지원 수준을 정의합니다.  
  
## UI 요소 목록  
 **컨트롤 형식**  
 만들려는 컨트롤의 형식을 지정합니다.  
  
-   **표준 컨트롤: ActiveX 컨트롤**  
  
-   **합성 컨트롤**: 대화 상자와 유사하게 다른 ActiveX 컨트롤이나 Windows 컨트롤을 포함할 수 있는 ActiveX 컨트롤입니다.  복합 컨트롤에는 다음과 같은 것이 포함됩니다.  
  
    -   복합 컨트롤을 구현하는 대화 상자의 템플릿  
  
    -   호출할 때 복합 컨트롤을 자동으로 등록하는 사용자 지정 리소스인 REGISTRY  
  
    -   복합 컨트롤을 구현하는 C\+\+ 클래스  
  
    -   복합 컨트롤에 의해 노출되는 COM 인터페이스  
  
    -   복합 컨트롤을 포함하는 HTML 테스트 페이지  
  
     기본적으로 이 컨트롤은 [CComControlBase::m\_bWindowOnly](../Topic/CComControlBase::m_bWindowOnly.md)를 true로 설정하여 창 있는 컨트롤임을 나타냅니다.  이 컨트롤은 싱크 맵을 구현합니다.  자세한 내용은 [DHTML 컨트롤에 대한 지원](../../atl/atl-support-for-dhtml-controls.md)을 참조하십시오.  
  
-   **DHTML 컨트롤**: ATL DHTML 컨트롤은 HTML을 사용하여 사용자 인터페이스를 지정합니다.  DHTML UI 클래스에는 COM 맵이 포함됩니다.  기본적으로 이 컨트롤은 [CComControlBase::m\_bWindowOnly](../Topic/CComControlBase::m_bWindowOnly.md)를 true로 설정하여 창 있는 컨트롤임을 나타냅니다.  
  
     자세한 내용은 [Identifying the Elements of the DHTML Control Project](../../atl/identifying-the-elements-of-the-dhtml-control-project.md)을 참조하십시오.  
  
 **최소 컨트롤**  
 대부분의 컨테이너에서 반드시 필요로 하는 인터페이스만 지원합니다.  모든 컨트롤 형식에 대해 **최소 컨트롤**을 설정할 수 있습니다. 즉, 최소 표준 컨트롤, 최소 복합 컨트롤, 최소 DHTML 컨트롤 등을 만들 수 있습니다.  
  
 **집계**  
 만들고 있는 컨트롤에 집합체 지원을 추가합니다.  자세한 내용은 [Aggregation](../../atl/aggregation.md)을 참조하십시오.  
  
-   **예**: 집합체를 허용하는 컨트롤을 만듭니다.  
  
-   **아니요**: 집합체를 허용하지 않는 컨트롤을 만듭니다.  
  
-   **전용**: 집합체를 통해서만 인스턴스화할 수 있는 컨트롤을 만듭니다.  
  
 **스레딩 모델**  
 컨트롤에서 사용하는 스레딩 모델을 지정합니다.  
  
-   **단일**: 컨트롤은 주 COM 스레드에서만 실행됩니다.  
  
-   **아파트**: 컨트롤은 모든 단일 스레드 아파트에서 만들 수 있습니다.  기본값입니다.  
  
 **Interface**  
 이 컨트롤에서 컨테이너에 노출하는 인터페이스 형식을 지정합니다.  
  
-   **이중**: `IDispatch`와 VTBL을 통해 속성과 메서드를 노출하는 인터페이스를 만듭니다.  
  
-   **사용자 지정**: VTBL을 통해 메서드를 직접 노출하는 인터페이스를 만듭니다.  
  
     **사용자 지정**을 선택하면 컨트롤을 **자동화 호환**으로 지정할 수 있습니다.  **자동화 호환**을 선택하면 IDL의 인터페이스에 [oleautomation](../../windows/oleautomation.md) 특성이 추가되고, 인터페이스는 oleaut32.dll에 있는 범용 마샬러를 통해 마샬링될 수 있습니다.  자세한 내용은 [!INCLUDE[winsdkshort](../../atl/reference/includes/winsdkshort_md.md)]의 [Marshaling Details](http://msdn.microsoft.com/library/windows/desktop/ms692621)를 참조하십시오.  
  
     또한 **자동화 호환**을 선택하면 컨트롤에 있는 모든 메서드의 모든 매개 변수가 **VARIANT** 형식과 호환되어야 합니다.  
  
 **지원**  
 컨트롤에 기타 추가 지원을 설정합니다.  
  
-   **연결 지점**: 개체의 클래스가 [IConnectionPointContainerImpl](../../atl/reference/iconnectionpointcontainerimpl-class.md)에서 파생되고 소스 인터페이스에 노출되도록 하여 개체의 연결 지점을 활성화합니다.  
  
-   **라이선스 지원**: 컨트롤에 [라이선스](http://msdn.microsoft.com/library/windows/desktop/ms690543)에 대한 지원을 추가합니다.  라이선스가 있는 컨트롤은 클라이언트 컴퓨터에 올바른 라이선스가 있을 경우에만 호스팅할 수 있습니다.  
  
## 참고 항목  
 [ATL 컨트롤 마법사](../../atl/reference/atl-control-wizard.md)