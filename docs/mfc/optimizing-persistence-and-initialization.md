---
title: "지 속성 및 초기화 최적화 | Microsoft Docs"
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
- MFC ActiveX controls [MFC], optimizing
- performance, ActiveX controls
- optimization, ActiveX controls
- optimizing performance, ActiveX controls
ms.assetid: e821e19e-b9eb-49ab-b719-0743420ba80b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: eeddfe4c67de2e96d42c7714619463ae3be45187
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="optimizing-persistence-and-initialization"></a>지속성 및 초기화 최적화
지 속성 및 초기화 컨트롤에서 기본적으로 처리는 `DoPropExchange` 멤버 함수입니다. 일반적인 컨트롤에서이 함수를 몇 개의 호출을 포함 **PX_** 함수 (`PX_Color`, `PX_Font`등), 각 속성에 대 한 합니다.  
  
 이러한 접근 방식은 이점이 있는 단일 `DoPropExchange` 초기화를 위해, 이진 형식에 대 한 일부 컨테이너에서 사용 하는 소위 "속성 모음" 형식에서 지 속성 구현을 사용할 수 있습니다. 이 함수는 속성과 편리 하 게 한 곳에서 해당 기본값에 대 한 모든 정보를 제공 합니다.  
  
 그러나이 generality 대신 효율성 듭니다. **PX_** 함수 가져오기 적음에도 본질적으로 다중 계층된 구현을 통해 유연성 보다 직접적 하지만 덜 효율적 방법 보다 효율적입니다. 또한 컨트롤에 기본 값을 전달 하는 경우는 **PX_** 함수는 기본값 기본값 있습니다 사용할 필요가 없을 때에도 항상을 제공 해야 합니다. 기본값을 생성 하는 것은 간단 하지 않은 작업 (예: 값 앰비언트 속성에서 가져온 경우), 다음 추가 하는 경우 기본값은 사용 되지 않는 경우에서 불필요 한 작업이 수행 됩니다.  
  
 컨트롤의 재정의 하 여 컨트롤의 이진 지 속성 성능은 향상 시킬 수 있습니다 `Serialize` 함수입니다. 기본 구현은이 멤버 함수를 호출 하 여 `DoPropExchange` 함수입니다. 멤버 함수를 재정의 하 여 이진 지 속성에 대 한 직접적 구현을 제공할 수 있습니다. 예를 들어,이 점을 고려해 `DoPropExchange` 함수:  
  
 [!code-cpp[NVC_MFC_AxOpt#1](../mfc/codesnippet/cpp/optimizing-persistence-and-initialization_1.cpp)]  
  
 이 컨트롤의 이진 지 속성의 성능을 향상 시키기 위해 재정의할 수 있습니다는 `Serialize` 다음과 같이 작동 합니다.  
  
 [!code-cpp[NVC_MFC_AxOpt#2](../mfc/codesnippet/cpp/optimizing-persistence-and-initialization_2.cpp)]  
  
 `dwVersion` 컨트롤의 영구 상태 버전 로드 되거나 저장 되 고 검색 하는 로컬 변수를 사용할 수 있습니다. 이 변수를 사용 하 여 호출 하는 대신 [CPropExchange::GetVersion](../mfc/reference/cpropexchange-class.md#getversion)합니다.  
  
 작은 공간에 대 한 영구 형식으로 저장 하는 **BOOL** 속성 (에서 생성 되는 형식과 호환 되도록 하기 `PX_Bool`), 속성으로 저장할 수 있습니다는 **바이트**다음과 같이:  
  
 [!code-cpp[NVC_MFC_AxOpt#3](../mfc/codesnippet/cpp/optimizing-persistence-and-initialization_3.cpp)]  
  
 캐스팅 하는 것이 아니라 임시 변수를 사용한 부하의 경우 해당 값이 할당 되며 `m_boolProp` 에 **바이트** 참조 합니다. 1 바이트의 캐스팅 방법을 초래 `m_boolProp` 수정 하 고, 나머지 바이트는 초기화 되지 않았습니다.  
  
 동일한 컨트롤에 대 한 재정의 하 여 컨트롤의 초기화를 최적화할 수 [COleControl::OnResetState](../mfc/reference/colecontrol-class.md#onresetstate) 다음과 같습니다.  
  
 [!code-cpp[NVC_MFC_AxOpt#4](../mfc/codesnippet/cpp/optimizing-persistence-and-initialization_4.cpp)]  
  
 하지만 `Serialize` 및 `OnResetState` 재정의 되었는지는 `DoPropExchange` 함수 유지할지 그대로 속성 모음의 형태로 지 속성을 위해 계속 사용 되므로 합니다. 세 가지 메커니즘 컨테이너는 지 속성에 관계 없이 사용 하 여 이러한 함수는 컨트롤이 해당 속성을 일관 되 게 관리 되도록 유지 하는 것이 유용 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC ActiveX 컨트롤: 최적화](../mfc/mfc-activex-controls-optimization.md)

