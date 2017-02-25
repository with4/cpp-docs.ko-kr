---
title: "Understanding Window Traits | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "window traits"
ms.assetid: c90cf850-9e91-49da-9cf3-ad4efb30347d
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Understanding Window Traits
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

창 특성 클래스는 ATL 창 개체를 만드는 데 사용 되는 스타일을 표준화 하기 위한 간단한 메서드를 제공 합니다.  창 특성에서 템플릿 매개 변수로 허용 됩니다  [CWindowImpl](../atl/reference/cwindowimpl-class.md) 및 다른 ATL 창 클래스의 기본 창 스타일 클래스 수준에서 제공 하는 방법으로.  
  
 창 인스턴스를 만든 스타일 호출에서 명시적으로 제공 하지 않는 경우  [만들기](../Topic/CWindowImpl::Create.md), 특성 클래스를 사용 하 여 창의 올바른 스타일으로 여전히 만들어졌는지 확인 합니다.  경우에 특정 스타일 창 클래스의 모든 인스턴스를 다른 스타일을 허용 하는 동안 인스턴스 당 기준으로 설정 설정 되어 있는지 확인할 수 있습니다.  
  
## ATL 창 특성 템플릿  
 ATL은 자체 템플릿 매개 변수를 사용 하 여 컴파일 타임에 기본 스타일을 설정할 수 있는 두 개의 창 특성 템플릿을 제공 합니다.  
  
|클래스|설명|  
|---------|--------|  
|[용으로 CWinTraits](../atl/reference/cwintraits-class.md)|창 스타일만 다른 스타일이 호출에 지정 된 경우 사용할 기본값을 제공 하려는 경우이 서식 파일 사용  **만들기**.  컴파일 타임에 우선 실행된 시간에 설정 된 스타일을 통해 제공 되는 스타일입니다.|  
|[CWinTraitsOR](../atl/reference/cwintraitsor-class.md)|항상 창 클래스를 설정 해야 하는 스타일을 지정 하려면이 클래스를 사용 합니다.  런타임에 제공 되는 스타일 비트 OR 연산자를 사용 하 여 컴파일 타임에 설정 된 스타일으로 결합 됩니다.|  
  
 이러한 템플릿 외에도 여러 개의 미리 정의 된 특수화의 ATL을 제공 된 `CWinTraits` 창 스타일 조합을 자주 사용 하는 템플릿.  참조는  [용으로 CWinTraits](../atl/reference/cwintraits-class.md) 설명서를 참조 합니다.  
  
## 사용자 지정 창 특성  
 ATL에서 제공 되는 템플릿의 전문화 한 드문 경우에 충분 하지 않 및 사용자 지정 특성 클래스를 만들어야 할 두 개의 정적 함수를 구현 하는 클래스를 만들 필요가: `GetWndStyle` 및  **GetWndStyleEx**.  
  
 [!code-cpp[NVC_ATL_Windowing#68](../atl/codesnippet/CPP/understanding-window-traits_1.h)]  
  
 이러한 각 함수 일부 스타일 값 사용 하 여 새 스타일 값을 생성 하는 실행된 시간에 전달 됩니다.  ATL 창 클래스를 템플릿 인수로 창 특성 클래스를 사용 하는 경우 스타일 값이 정적 함수에 전달 된 모든 항목에 스타일 인수로 전달 된 됩니다  [만들기](../Topic/CWindowImpl::Create.md).  
  
## 참고 항목  
 [창 클래스](../atl/atl-window-classes.md)