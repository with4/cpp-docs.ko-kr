---
title: "MFC ActiveX 컨트롤: 앰비언트 속성 액세스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], accessing ambient properties
- properties [MFC], accessing ambient
ms.assetid: fdc9db29-e6b0-45d2-a879-8bd60e2058a7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b05e6d37a0550cf157dcd43a22689c9db029b51f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="mfc-activex-controls-accessing-ambient-properties"></a>MFC ActiveX 컨트롤: 앰비언트 속성 액세스
이 문서에서는 ActiveX 컨트롤 컨트롤 컨테이너의 앰비언트 속성에 액세스할 수는 방법을 설명 합니다.  
  
 컨트롤은 컨테이너의 앰비언트 속성에 액세스 하 여 해당 컨테이너에 대 한 정보를 얻을 수 있습니다. 이러한 속성은 컨테이너의 배경색을 컨테이너 인지 현재 사용자 모드 또는 디자이너 모드와 같은 컨테이너 및 작업 특성에서 사용 하는 현재 글꼴 등의 시각적 특성을 노출 합니다. 컨트롤의 모양 및 동작이 포함 된 특정 컨테이너에 맞게 앰비언트 속성에서 사용할 수 있습니다. 그러나 컨트롤은 해당 컨테이너에서 모든 앰비언트 속성을 지원 하는지을 가정 하지 않아야 합니다. 실제로 일부 컨테이너는 앰비언트 속성을 전혀 지원 하지 않을 수 있습니다. 컨트롤은 앰비언트 속성이 없는 경우에는 적절 한 기본값을 가정해 야 합니다.  
  
 호출 하는 앰비언트 속성에 액세스 하려면 [COleControl::GetAmbientProperty](../mfc/reference/colecontrol-class.md#getambientproperty)합니다. 이 함수에서는 앰비언트 속성에 대 한 디스패치 ID (olectl 첫 번째 매개 변수로. H에서 정의 함 표준 집합).  
  
 매개 변수는 `GetAmbientProperty` 함수는 필요한 속성 형식 및 메모리에 대 한 포인터를 나타내는 변형 태그 디스패치 ID 값을 반환 해야 합니다. 이 포인터 참조 하는 데이터 형식을 variant 태그에 따라 달라 집니다. 함수 반환 **TRUE** 컨테이너 속성을 지 원하는 경우 그렇지 않으면 반환 **FALSE**합니다.  
  
 다음 코드 예제에서는 "UserMode" 이라는 앰비언트 속성의 값을 가져옵니다. 속성의 기본값을 컨테이너에서 지원 되지 않습니다 **TRUE** 것으로 간주 됩니다.  
  
 [!code-cpp[NVC_MFC_AxUI#30](../mfc/codesnippet/cpp/mfc-activex-controls-accessing-ambient-properties_1.cpp)]  
  
 사용자 편의 위해 `COleControl` 대부분의 자주 사용 되는 앰비언트 속성 액세스 및 속성을 사용할 수 없는 경우 적절 한 기본값을 반환 하는 도우미 함수를 제공 합니다. 이러한 도우미 함수는 다음과 같습니다.  
  
-   [COleControl::AmbientBackColor](../mfc/reference/colecontrol-class.md#ambientbackcolor)  
  
-   [AmbientDisplayName](../mfc/reference/colecontrol-class.md#ambientdisplayname)  
  
-   [AmbientFont](../mfc/reference/colecontrol-class.md#ambientfont)  
  
    > [!NOTE]
    >  호출자에 게 호출 해야 **()를 릴리스** 반환 되는 글꼴에 있습니다.  
  
-   [AmbientForeColor](../mfc/reference/colecontrol-class.md#ambientforecolor)  
  
-   [AmbientLocaleID](../mfc/reference/colecontrol-class.md#ambientlocaleid)  
  
-   [AmbientScaleUnits](../mfc/reference/colecontrol-class.md#ambientscaleunits)  
  
-   [AmbientTextAlign](../mfc/reference/colecontrol-class.md#ambienttextalign)  
  
-   [AmbientUserMode](../mfc/reference/colecontrol-class.md#ambientusermode)  
  
-   [AmbientUIDead](../mfc/reference/colecontrol-class.md#ambientuidead)  
  
-   [AmbientShowHatching](../mfc/reference/colecontrol-class.md#ambientshowhatching)  
  
-   [AmbientShowGrabHandles](../mfc/reference/colecontrol-class.md#ambientshowgrabhandles)  
  
 앰비언트 속성의 값 (작업 컨테이너의)을 통해 변경 되 면는 **OnAmbientPropertyChanged** 컨트롤의 멤버 함수를 호출 합니다. 이러한 알림 메시지를 처리 하려면이 멤버 함수를 재정의 합니다. 에 대 한 매개 변수 **OnAmbientPropertyChanged** 영향을 받는 앰비언트 속성의 디스패치 ID입니다. 이 디스패치 ID의 값이 경우도 **DISPID_UNKNOWN**, 하나 이상의 앰비언트 속성이 변경 되었지만 영향을 받은 속성에 대 한 정보를 사용할 수 없으면 나타냅니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)

