---
title: 탭 및 탭 컨트롤 특성 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- attributes [MFC], reference topics
- tab controls [MFC], attributes
- tabs [MFC]
- tabs [MFC], attributes
- CTabCtrl class [MFC], tab control attributes
ms.assetid: ecf190cb-f323-4751-bfdb-766dbe6bb553
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f925f8b6a5c522e22890ee2c1082ae8d709d2220
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="tabs-and-tab-control-attributes"></a>탭 및 탭 컨트롤 특성
모양 및 탭 컨트롤을 구성 하는 탭의 동작을 상당히 제어할 수 있습니다 ([CTabCtrl](../mfc/reference/ctabctrl-class.md)). 각 탭 레이블, 아이콘, 항목 상태 및 연결 된 하는 응용 프로그램 정의 32 비트 값을 포함할 수 있습니다. 각 탭에 대 한 아이콘, 레이블, 또는 둘 모두를 표시할 수 있습니다.  
  
 각 탭 항목 상태를 가질 수는 또한: 누름, 누르지 않은 상태 또는 강조 표시 합니다. 이 상태는 기존 탭 항목을 수정 하 여 설정할 수만 있습니다. 기존 탭 항목을 수정 하려면 호출 하 여 검색 [GetItem](../mfc/reference/ctabctrl-class.md#getitem), 수정 된 `TCITEM` 구조 (구체적으로 **dwState** 및 **dwStateMask** 데이터 멤버 )를 한 다음 수정 된 반환 `TCITEM` 을 호출 하 여 구조 [SetItem](../mfc/reference/ctabctrl-class.md#setitem)합니다. 항목 상태에 있는 모든 탭 항목의 선택을 취소 해야 하는 경우는 `CTabCtrl` 개체에 대 한 호출을 확인, [DeselectAll](../mfc/reference/ctabctrl-class.md#deselectall)합니다. 이 함수는 모든 탭 항목 또는 현재 선택 된 노드를 제외한 모든 항목의 상태를 다시 설정 합니다.  
  
 다음 코드는 모든 탭 항목의 상태를 지운 하 고 세 번째 항목의 상태를 수정 합니다.  
  
 [!code-cpp[NVC_MFCControlLadenDialog#32](../mfc/codesnippet/cpp/tabs-and-tab-control-attributes_1.cpp)]  
  
 탭 특성에 대 한 자세한 내용은 참조 [탭 및 탭 특성](http://msdn.microsoft.com/library/windows/desktop/bb760550) Windows sdk에서입니다. 탭 컨트롤에 탭을 추가 하는 방법에 대 한 자세한 내용은 참조 [탭 컨트롤에 탭 추가](../mfc/adding-tabs-to-a-tab-control.md) 이 항목의 뒷부분에 나오는 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CTabCtrl 사용](../mfc/using-ctabctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

