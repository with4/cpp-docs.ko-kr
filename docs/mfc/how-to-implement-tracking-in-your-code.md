---
title: "방법: 코드에서 추적 구현 | Microsoft Docs"
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
- CRectTracker class [MFC], implementing trackers
ms.assetid: baaeca2c-5114-485f-bf58-8807db1bc973
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2ad49c70113780e0c0570e88efab06efc347e83d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-implement-tracking-in-your-code"></a>방법: 코드에서 추적 구현
OLE 항목을 추적 하려면 항목 클릭 또는 문서는 뷰를 업데이트 하는 등의 항목에 관련 된 특정 이벤트를 처리 해야 합니다. 모든 경우에는 임시 선언할 수는 [CRectTracker](../mfc/reference/crecttracker-class.md) 개체 및이 개체를 사용 하 여 항목을 조작 합니다.  
  
 사용자가 항목을 선택 하거나 메뉴 명령 사용 하 여 개체를 삽입, 추적기 OLE 항목의 상태를 나타내는 적절 한 스타일으로 초기화 해야 합니다. 다음 표에서 OCLIENT 샘플에서 사용 되는 규칙을 설명 합니다. 이러한 스타일에 대 한 자세한 내용은 참조 하십시오. `CRectTracker`합니다.  
  
### <a name="container-styles-and-states-of-the-ole-item"></a>컨테이너 스타일 및 해당 OLE 항목의 상태  
  
|표시 스타일|OLE 항목의 상태|  
|---------------------|-----------------------|  
|점선된 테두리|항목을 연결|  
|실선|문서에 포함 된 항목|  
|크기 조정 핸들|현재 선택 된 항목이|  
|빗살 무늬 테두리|Item은 현재 내부 활성화|  
|빗살 무늬로 채워진 항목|항목의 서버는 열기|  
  
 OLE 항목의 상태를 확인 하 고 적절 한 스타일을 설정 하는 프로시저를 사용 하 여 쉽게이 초기화를 처리할 수 있습니다. **SetupTracker** OCLIENT 샘플에서 찾을 수 함수 추적기 초기화를 보여 줍니다. 이 함수에 대 한 매개 변수는 추적기 주소 *pTracker*;는 추적기와 관련 클라이언트 항목에 대 한 포인터 `pItem`; 및 사각형에 대 한 포인터 *pTrueRect*합니다. 이 함수는 보다 완전 예제를 보려면 MFC OLE 샘플 [OCLIENT](../visual-cpp-samples.md)합니다.  
  
 **SetupTracker** 코드 예제에서는 단일 함수를 제공 하며, 함수의 줄 함수의 기능을 설명 하면서 섞여 있습니다.  
  
 [!code-cpp[NVC_MFCOClient#1](../mfc/codesnippet/cpp/how-to-implement-tracking-in-your-code_1.cpp)]  
  
 추적기 최소 크기를 설정 하는 추적기의 스타일을 선택을 취소 하 여 초기화 됩니다.  
  
 [!code-cpp[NVC_MFCOClient#2](../mfc/codesnippet/cpp/how-to-implement-tracking-in-your-code_2.cpp)]  
  
 다음 줄 항목 현재 선택 되어 있는지 여부 및 항목은 문서에 연결 또는 항목에 포함 된 참조를 확인 합니다. 테두리 내부에 있는 크기 조정 핸들이 현재 항목이 선택 되어 있는지를 나타내는 스타일에 추가 됩니다. 항목은 문서에 연결 되어 있는 경우 점선된 테두리 스타일이 사용 됩니다. 단색 테두리가 항목이 포함 된 경우에 사용 됩니다.  
  
 [!code-cpp[NVC_MFCOClient#3](../mfc/codesnippet/cpp/how-to-implement-tracking-in-your-code_3.cpp)]  
  
 다음 코드 오버레이 항목을 현재 빗살 무늬로으로 표시 된 항목을 엽니다.  
  
 [!code-cpp[NVC_MFCOClient#4](../mfc/codesnippet/cpp/how-to-implement-tracking-in-your-code_4.cpp)]  
  
 추적기를 표시 해야 할 때마다이 함수를 호출할 수 있습니다. 이 함수를 호출 하는 예를 들어는 `OnDraw` 뷰 클래스의 함수입니다. 추적기의 모양이 뷰가 다시 표시 될 때마다 업데이트 됩니다. 전체 예제에 대 한 참조는 **CMainView::OnDraw** MFC OLE 샘플의 기능 [OCLIENT](../visual-cpp-samples.md)합니다.  
  
 응용 프로그램에서 추적기 코드 크기 조정, 이동 또는 검색 하 고, 같은 필요한 이벤트를 발생 합니다. 이러한 작업을 선택 하거나 항목을 이동 하는 시도가 이루어집니다 되 고 일반적으로 나타냅니다. 이러한 경우 작업을 선택 했는지를 결정 해야 합니다: 크기 조정 핸들을 크기 조정 핸들 또는 사이의 테두리의 일부입니다. `OnLButtonDown` 메시지 처리기는 항목을 기준으로 마우스의 상대 위치를 테스트 하는 것이 좋습니다. 호출할 `CRectTracker::HitTest`합니다. 테스트 이외의 값을 반환 하는 경우 **CRectTracker::hitOutside**, 항목 크기를 조정 하거나 이동 중인 됩니다. 따라서,에 대 한 호출을 확인 해야는 `Track` 멤버 함수입니다. 참조는 **CMainView::OnLButtonDown** 함수 MFC OLE 샘플에 있는 [OCLIENT](../visual-cpp-samples.md) 는 전체 예제입니다.  
  
 `CRectTracker` 클래스는 작업이 발생 하는 이동, 크기 조정 또는 끌어 있는지 여부를 나타내는 데 사용 되는 다양 한 커서 모양을 제공 합니다. 이 이벤트를 처리 하려면으로 마우스 현재 항목이 선택 되었는지 여부를 확인 하십시오. 인 경우 확인에 대 한 호출 `CRectTracker::SetCursor`, 하거나 기본 처리기를 호출 합니다. 다음 예제는 MFC OLE 샘플에서 [OCLIENT](../visual-cpp-samples.md):  
  
 [!code-cpp[NVC_MFCOClient#5](../mfc/codesnippet/cpp/how-to-implement-tracking-in-your-code_5.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [추적기: OLE 응용 프로그램에서 추적기 구현](../mfc/trackers-implementing-trackers-in-your-ole-application.md)

