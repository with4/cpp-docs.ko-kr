---
title: 고무 밴드 및 추적기 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- trackers [MFC]
- CRectTracker class [MFC], implementing trackers
- OLE objects [MFC], selecting
- rubber banding [MFC]
- WM_LBUTTONDOWN [MFC]
ms.assetid: 0d0fa64c-6418-4baf-ab7f-2d16ca039230
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a4f36a634e4e5e6d4ee6c2618d0d43313c7c8094
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36931738"
---
# <a name="rubber-banding-and-trackers"></a>고무 밴드 및 추적기
추적기에 제공되는 또 다른 기능은 "고무 밴드" 선택 기능입니다. 이 기능을 통해 사용자는 선택할 항목 주위의 크기 조정 직사각형을 끌어서 여러 OLE 항목을 선택할 수 있습니다. 사용자가 왼쪽 마우스 단추를 놓으면 사용자가 선택한 영역 내에 있는 항목이 선택되고 사용자가 조작할 수 있는 상태가 됩니다. 예를 들어 사용자가 선택한 항목을 다른 컨테이너 응용 프로그램으로 끌어갈 수 있습니다.  
  
 이 기능을 구현 응용 프로그램의 WM_LBUTTONDOWN 처리기 함수에 일부 추가 코드가 필요 합니다.  
  
 다음 코드 샘플은 고무 밴드 선택 및 추가 기능을 구현합니다.  
  
 [!code-cpp[NVC_MFCOClient#6](../mfc/codesnippet/cpp/rubber-banding-and-trackers_1.cpp)]  
  
 고무 밴드 추적기의 방향을 허용 하려는 경우 호출 해야 [crecttracker:: Trackrubberband](../mfc/reference/crecttracker-class.md#trackrubberband) 로 설정 세 번째 매개 변수와 함께 **TRUE**합니다. 수 경우가 발생 하면 [M_rect](../mfc/reference/crecttracker-class.md#m_rect) 될 반전 합니다. 호출 하 여 해결할 수 [crect:: Normalizerect](../atl-mfc-shared/reference/crect-class.md#normalizerect)합니다.  
  
 자세한 내용은 참조 [컨테이너 클라이언트 항목](../mfc/containers-client-items.md) 및 [끌어서 놓기 사용자 지정](../mfc/drag-and-drop-customizing.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [추적기: OLE 응용 프로그램에서 추적기 구현](../mfc/trackers-implementing-trackers-in-your-ole-application.md)   
 [CRectTracker 클래스](../mfc/reference/crecttracker-class.md)
