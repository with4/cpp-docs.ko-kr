---
title: 이미지 목록과 헤더 컨트롤 함께 사용 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- header controls [MFC], image lists
- CHeaderCtrl class [MFC], image lists
- image lists [MFC], header controls
ms.assetid: d5e9b310-6278-406c-909c-eefa09549a47
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2da3737b54c53903f8fc8ff30cccba6165cbde45
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33382781"
---
# <a name="using-image-lists-with-header-controls"></a>이미지 목록과 헤더 컨트롤 함께 사용
헤더 항목에는 머리글 항목 내 이미지를 표시할 수가 있습니다. 연결 된 이미지 목록에 저장 된이 이미지를 16 x 16 픽셀 있고 목록 뷰 컨트롤에서 사용 되는 아이콘 이미지와 같은 특성을 보유 합니다. 이 동작을 성공적으로 구현 하기 위해 해야 먼저 및 이미지 목록 초기화 목록을 헤더 컨트롤과 연결 만들고에 이미지가 표시 되는 머리글 항목의 속성을 수정 합니다.  
  
 다음 절차에서는 헤더 컨트롤에 대 한 포인터를 사용 하 여 세부 정보를 보여 줍니다 (`m_pHdrCtrl`) 및 이미지 목록에 대 한 포인터 (`m_pHdrImages`).  
  
### <a name="to-display-an-image-in-a-header-item"></a>헤더 항목에 이미지를 표시 하려면  
  
1.  새 이미지 목록을 생성 (또는 기존 이미지 목록 개체를 사용 하 여)를 사용 하는 [CImageList](../mfc/reference/cimagelist-class.md) 생성자를 결과 포인터를 저장 합니다.  
  
2.  호출 하 여 새 이미지 목록 개체를 초기화 [CImageList::Create](../mfc/reference/cimagelist-class.md#create)합니다. 다음 코드는이 호출의 한 가지 예입니다.  
  
     [!code-cpp[NVC_MFCControlLadenDialog#15](../mfc/codesnippet/cpp/using-image-lists-with-header-controls_1.cpp)]  
  
3.  각 헤더 항목에 대 한 이미지를 추가 합니다. 다음 코드는 두 개의 미리 정의 된 이미지를 추가 합니다.  
  
     [!code-cpp[NVC_MFCControlLadenDialog#16](../mfc/codesnippet/cpp/using-image-lists-with-header-controls_2.cpp)]  
  
4.  호출 하 여 헤더 컨트롤과 함께 이미지 목록을 연결 [CHeaderCtrl::SetImageList](../mfc/reference/cheaderctrl-class.md#setimagelist)합니다.  
  
5.  연결 된 이미지 목록에서 이미지를 표시 하는 머리글 항목을 수정 합니다. 다음 예제에서 첫 번째 이미지 할당 `m_phdrImages`, 첫 번째 헤더 항목에 `m_pHdrCtrl`합니다.  
  
     [!code-cpp[NVC_MFCControlLadenDialog#17](../mfc/codesnippet/cpp/using-image-lists-with-header-controls_3.cpp)]  
  
 사용 되는 매개 변수 값에 자세한 내용은 참조는 관련 [CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)합니다.  
  
> [!NOTE]
>  동일한 이미지 목록을 사용 하 여 여러 컨트롤 것 같습니다. 예를 들어, 표준 목록 뷰 컨트롤에서 있을 수는 목록 뷰 컨트롤의 작은 아이콘 보기 및 목록 뷰 컨트롤의 헤더 항목에서 사용 하는 16 x 16 픽셀 이미지) (의 이미지 목록입니다.  
  
## <a name="see-also"></a>참고 항목  
 [CHeaderCtrl 사용](../mfc/using-cheaderctrl.md)

