---
title: "목록 컨트롤의 작업 영역 구현 | Microsoft Docs"
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
- list controls [MFC], working areas
- working areas in list control [MFC]
ms.assetid: fbbb356b-3359-4348-8603-f1cb114cadde
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cefb8007fd9b73dda4c0e8a99e9ae9daa1bfcc34
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="implementing-working-areas-in-list-controls"></a>리스트 컨트롤의 작업 영역 구현
기본적으로 목록 컨트롤에 표준 표 적절 하 게에 있는 모든 항목을 정렬합니다. 그러나 작업 영역을 사각형 그룹으로 목록 항목을 정렬 하는 다른 메서드는 지원 합니다. 작업 영역을 구현 하는 목록 컨트롤의 이미지에 대 한 Windows SDK에서 목록 뷰 컨트롤 사용를 참조 하십시오.  
  
> [!NOTE]
>  목록 컨트롤 아이콘 또는 작은 아이콘 모드에 있을 때만 작업 영역이 표시 됩니다. 그러나 현재 작업 영역은 보기 보고서 또는 목록을 모드로 전환 되는 경우 유지 됩니다.  
  
 영역 작업 (왼쪽, 위쪽 이나 항목의 오른쪽)에 빈 테두리를 표시 하거나 없을 하나 때 표시 될 가로 스크롤 막대를 사용할 수 있습니다. 일반적으로 사용 있는 항목 이동 하거나 수 삭제할 여러 작업 영역을 만드는 것입니다. 이 방법을 다른 의미를 갖는 단일 보기에 영역을 만들 수 있습니다. 그런 다음 사용자 다른 영역에 배치 하 여 항목을 분류할 수 있습니다. 이러한 예로 파일 시스템 읽기/쓰기 파일에 대 한 영역 및 읽기 전용 파일에 대 한 다른 영역에 대 한 뷰 것입니다. 파일 항목에는 읽기 전용 영역으로 이동한 경우 읽기 전용이 되 자동으로 합니다. 읽기 전용 영역에서 파일을 읽기/쓰기 영역으로 이동할 경우 파일 읽기/쓰기가 게 됩니다.  
  
 `CListCtrl`만들고 목록 컨트롤에서 작업 영역을 관리 하기 위한 몇 가지 멤버 함수를 제공 합니다. [GetWorkAreas](../mfc/reference/clistctrl-class.md#getworkareas) 및 [SetWorkAreas](../mfc/reference/clistctrl-class.md#setworkareas) 검색 하 고의 배열을 설정 `CRect` 개체 (또는 `RECT` 구조)는 목록 컨트롤에 대 한 현재 구현 된 작업 영역을 저장 합니다. 또한 [GetNumberOfWorkAreas](../mfc/reference/clistctrl-class.md#getnumberofworkareas) 영역 목록 컨트롤에 대 한 작업의 현재 수를 검색 (기본적으로 0).  
  
## <a name="items-and-working-areas"></a>항목 및 작업 영역  
 작업 영역이 만들어지면 작업 영역에 배치 된 항목 작업 영역의 멤버가 됩니다. 마찬가지로, 항목 작업 영역으로 이동 하 고, 작업 영역 이동 된 구성원이 됩니다. 어떤 작업 영역 내에 항목이 포함 되지 않는 경우 자동으로 첫 번째 (인덱스 0) 작업 영역 구성원을 됩니다. 항목을 만들고 다음을 호출 하 여 원하는 작업 영역으로 이동 해야 합니다는 항목을 만들고 특정 작업 영역 내에 배치 하 게 하려는 경우 [SetItemPosition](../mfc/reference/clistctrl-class.md#setitemposition)합니다. 아래의 두 번째 예제에는이 기술을 보여 줍니다.  
  
 다음 예에서는 4 개의 작업 영역 구현 (`rcWorkAreas`), 10 픽셀 너비 목록 컨트롤에서 각 작업 영역에 테두리와 동일한 크기의 (`m_WorkAreaListCtrl`).  
  
 [!code-cpp[NVC_MFCControlLadenDialog#20](../mfc/codesnippet/cpp/implementing-working-areas-in-list-controls_1.cpp)]  
  
 에 대 한 호출 [ApproximateViewRect](../mfc/reference/clistctrl-class.md#approximateviewrect) 지역에서 모든 항목을 표시 하는 데 필요한 전체 영역의 추정치를 얻기 위해 만들어졌습니다. 이 예상 4 개의 영역으로 분할 되어 5 픽셀 너비 테두리 채워집니다.  
  
 다음 예에서는 각 그룹에 기존 목록 항목을 할당 (`rcWorkAreas`) 컨트롤 뷰를 새로 고칩니다 (`m_WorkAreaListCtrl`) 효과 완료 합니다.  
  
 [!code-cpp[NVC_MFCControlLadenDialog#21](../mfc/codesnippet/cpp/implementing-working-areas-in-list-controls_2.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [CListCtrl 사용](../mfc/using-clistctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

