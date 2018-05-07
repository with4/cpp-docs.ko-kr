---
title: 잘리지 않는 장치 컨텍스트를 사용 하 여 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], unclipped device context
ms.assetid: 9c020063-73da-4803-bf7b-2e1fd950c9ed
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8c76dc44993615e17ea3d99f9ac018a748e24d0a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="using-an-unclipped-device-context"></a>잘리지 않는 장치 컨텍스트 사용
에 대 한 호출을 사용 하지 않도록 설정 하 여 감지 하지만 크기가 작은 속도 향상을 실현할 수 인 경우 반드시 특정 컨트롤의 클라이언트 영역 밖에 그리지 않는 `IntersectClipRect` 으로 되기 `COleControl`합니다. 이 작업을 수행 하려면 제거의 **clipPaintDC** 에서 반환 하는 플래그 집합의 플래그 [COleControl::GetControlFlags](../mfc/reference/colecontrol-class.md#getcontrolflags)합니다. 예를 들어:  
  
 [!code-cpp[NVC_MFC_AxOpt#5](../mfc/codesnippet/cpp/using-an-unclipped-device-context_1.cpp)]  
[!code-cpp[NVC_MFC_AxOpt#14](../mfc/codesnippet/cpp/using-an-unclipped-device-context_2.cpp)]  
[!code-cpp[NVC_MFC_AxOpt#7](../mfc/codesnippet/cpp/using-an-unclipped-device-context_3.cpp)]  
  
 선택 하는 경우이 플래그를 제거 하는 코드는 자동으로 생성 됩니다는 **잘리지 않는 장치 컨텍스트** 옵션에 [제어 설정](../mfc/reference/control-settings-mfc-activex-control-wizard.md) MFC ActiveX 컨트롤 마법사와 컨트롤을 만들 때 페이지.  
  
 창 없는 활성화를 사용 하는 경우이 최적화에 영향을 주지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC ActiveX 컨트롤: 최적화](../mfc/mfc-activex-controls-optimization.md)

